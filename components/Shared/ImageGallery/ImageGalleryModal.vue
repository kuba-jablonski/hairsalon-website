<template>
  <div
    v-show="show"
    class="modal"
    @click="close"
  >
    <button
      class="btn btn--left"
      @click.stop="back"
    >
      <icon-left class="icon" />
    </button>
    <img class="img" :src="items[activeItemIndex].img" @click.stop>
    <button
      class="btn btn--right"
      @click.stop="forward"
    >
      <icon-right class="icon" />
    </button>
    <button
      class="btn btn--close"
      @click.stop="close"
    >
      <icon-close class="icon" />
    </button>
  </div>
</template>

<script>
import IconLeft from '~/assets/images/chevron-left.svg?inline'
import IconRight from '~/assets/images/chevron-right.svg?inline'
import IconClose from '~/assets/images/close.svg?inline'

export default {
  components: {
    IconLeft,
    IconRight,
    IconClose
  },
  props: {
    show: Boolean,
    activeItemIndex: Number,
    items: Array
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
    },
    back() {
      this.$emit('changeIndex', this.activeItemIndex - 1)
    },
    forward() {
      this.$emit('changeIndex', this.activeItemIndex + 1)
    }
  }
}
</script>


<style lang="scss" scoped>
.img {
  max-width: 99%;
  max-height: 99%;
}

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

  &--left {
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
  }

  &--right {
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
  }

  .icon {
    width: 5rem;
    height: 5rem;
    fill: white;
  }

  &:hover {
    opacity: 1;
  }

  @include respond(sm) {
    width: 6rem;
    height: 7rem;

    .icon {
      width: 3rem;
      height: 3rem;
    }
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
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
