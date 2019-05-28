<template>
  <div>
    <layout-nav id="top" />
    <nuxt />
    <layout-footer />
    <transition name="show">
      <a
        v-if="showBtn"
        v-smooth-scroll
        href="#top"
        class="btn-scroll"
      >
        <chevron-up-icon class="icon" />
      </a>
    </transition>
  </div>
</template>

<script>
import LayoutNav from '~/components/Layout/LayoutNav/LayoutNav'
import LayoutFooter from '~/components/Layout/LayoutFooter'
import ChevronUpIcon from '~/assets/images/chevron-up.svg?inline'

export default {
  components: {
    LayoutNav,
    LayoutFooter,
    ChevronUpIcon
  },
  data() {
    return {
      showBtn: false
    }
  },
  mounted() {
    const scrollHandler = () => {
      if (window.pageYOffset > 100) {
        this.showBtn = true
      } else {
        this.showBtn = false
      }
    }

    document.addEventListener('scroll', scrollHandler)
    this.$once('hook:destroyed', () => {
      document.removeEventListener('keydown', scrollHandler)
    })
  }
}
</script>

<style lang="scss" scoped>
.btn-scroll {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 4rem;
  height: 4rem;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: $color-primary;
  z-index: 100;
  box-shadow: 0 0 30px rgba(black, 0.5);
  transition: all 0.3s;

  &:hover {
    background-color: $color-font-dark;
  }
}

.icon {
  width: 1.5rem;
  height: 1.5rem;
  fill: white;
}

.show-enter-active,
.show-leave-active {
  transition: all 0.3s;
}
.show-enter, .show-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: scale(0);
}
</style>
