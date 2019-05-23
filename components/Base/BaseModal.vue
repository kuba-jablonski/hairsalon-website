<template>
  <div
    v-if="show"
    class="modal"
    :style="modalStyle"
    @click="close"
  >
    <slot />
    <button
      class="btn btn--close"
      @click.stop="close"
    >
      <icon-close class="icon" />
    </button>
  </div>
</template>

<script>
import IconClose from '~/assets/images/close.svg?inline'

export default {
  components: {
    IconClose
  },
  props: {
    show: Boolean,
    center: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    modalStyle() {
      if (this.center) {
        return {
          display: 'flex',
          'align-items': 'center',
          'justify-content': 'center'
        }
      } else return {}
    }
  },
  watch: {
    show(show) {
      process.browser && show
        ? document.body.style.setProperty('overflow', 'hidden')
        : document.body.style.removeProperty('overflow')
    }
  },
  created() {
    const escapeHandler = e => {
      if (e.key === 'Escape' && this.show) this.close()
    }

    if (process.browser) {
      document.addEventListener('keydown', escapeHandler)
      this.$once('hook:destroyed', () => {
        document.removeEventListener('keydown', escapeHandler)
      })
    }
  },
  methods: {
    close() {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss" scoped>
.btn {
  background-color: $color-primary;
  opacity: 0.8;
  border: none;
  outline: none;
  width: 9rem;
  height: 10rem;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: opacity 0.3s;

  &:hover {
    opacity: 1;
  }

  &--close {
    position: absolute;
    top: 2rem;
    right: 2rem;
    width: 3rem;
    height: 3rem;

    .icon {
      width: 2rem;
      height: 2rem;
      fill: white;
    }
  }
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 100;
}
</style>
