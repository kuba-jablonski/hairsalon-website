<template>
  <div
    v-show="show"
    class="modal"
  >
    <button>back</button>
    <img src="~/assets/images/9.jpg">
    <button>forward</button>
    <button
      class="btn-close"
      @click="close"
    >
      close
    </button>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean
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
.modal {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.btn-close {
  position: absolute;
  top: 2rem;
  right: 2rem;
}
</style>
