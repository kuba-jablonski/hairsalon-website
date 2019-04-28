<template>
  <div class="container">
    <nav class="nav">
      <img
        class="nav__logo"
        src="~/assets/images/logo.png"
        alt="Akame"
      >
      <ul class="nav__items">
        <nuxt-link
          to="/"
          class="nav__item"
        >
          Home
        </nuxt-link>
        <nuxt-link
          to="/portfolio"
          class="nav__item"
        >
          Portfolio
        </nuxt-link>
        <nuxt-link
          to="/services"
          class="nav__item"
        >
          Services
        </nuxt-link>
        <nuxt-link
          to="/about"
          class="nav__item"
        >
          About Us
        </nuxt-link>
        <nuxt-link
          to="/blog"
          class="nav__item"
        >
          Blog
        </nuxt-link>
        <nuxt-link
          to="/contact"
          class="nav__item"
        >
          Contact
        </nuxt-link>
      </ul>
      <transition name="slide">
        <div
          v-if="navOpen"
          class="nav-mobile"
        >
          <button
            class="nav-mobile__close-btn"
            @click="navOpen = false"
          >
            <icon-close class="nav-mobile__icon" />
          </button>
          <ul class="nav-mobile__items">
            <nuxt-link
              to="/"
              class="nav-mobile__item"
            >
              Home
            </nuxt-link>
            <nuxt-link
              to="/portfolio"
              class="nav-mobile__item"
            >
              Portfolio
            </nuxt-link>
            <nuxt-link
              to="/services"
              class="nav-mobile__item"
            >
              Services
            </nuxt-link>
            <nuxt-link
              to="/about"
              class="nav-mobile__item"
            >
              About Us
            </nuxt-link>
            <nuxt-link
              to="/blog"
              class="nav-mobile__item"
            >
              Blog
            </nuxt-link>
            <nuxt-link
              to="/contact"
              class="nav-mobile__item"
            >
              Contact
            </nuxt-link>
          </ul>
          <base-button class="nav-mobile__cta">
            Book Now
          </base-button>
        </div>
      </transition>
      <button
        class="menu-btn"
        @click="navOpen = !navOpen"
      >
        <icon-menu class="menu-btn__icon" />
      </button>
      <base-button class="nav__cta">
        Book Now
      </base-button>
    </nav>
  </div>
</template>

<script>
import IconClose from '~/assets/images/close.svg?inline'
import IconMenu from '~/assets/images/menu.svg?inline'

export default {
  components: {
    IconClose,
    IconMenu
  },
  data() {
    return {
      navOpen: false
    }
  }
}
</script>


<style lang="scss" scoped>
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.5s;
}
.slide-enter,
.slide-leave-to {
  transform: translateX(-100%);
}

.menu-btn {
  border: none;
  outline: none;
  background: transparent;
  display: none;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  &__icon {
    width: 3.5rem;
    height: 3.5rem;
    fill: #858585;
  }

  @include respond(md) {
    display: flex;
  }
}

.nav-mobile {
  position: fixed;
  top: 0;
  left: 0;
  width: 30rem;
  max-width: 100%;
  height: 100vh;
  background-color: white;
  z-index: 10;
  display: flex;
  flex-direction: column;
  box-shadow: 1px 0 5px rgba(0, 0, 0, 0.12);

  &__cta {
    margin-top: 2rem;
    align-self: center;
  }

  &__close-btn {
    padding: 1.5rem 2rem;
    align-self: flex-end;
    border: none;
    outline: none;
    background: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }

  &__icon {
    display: block;
    position: relative;
    right: 0;
    fill: #858585;
  }

  &__items {
    display: flex;
    flex-direction: column;
  }

  &__item {
    font-size: 1.4rem;
    background-color: #f2f4f8;
    border-bottom: 1px solid rgba(255, 255, 255, 0.5);
    padding: 1rem;
    transition: all 0.3s;

    &:hover {
      color: $color-primary;
    }
  }
}

.nav {
  background-color: #fff;
  display: flex;
  height: 10rem;
  align-items: center;

  &__logo {
    margin-right: auto;
  }

  &__items {
    display: flex;

    @include respond(md) {
      display: none;
    }
  }

  &__cta {
    margin-left: 5rem;

    @include respond(md) {
      display: none !important;
    }
  }

  &__item {
    padding: 0.4rem 0.6rem;
    margin: 0 1rem;
    transition: color 0.3s;

    &:hover {
      color: $color-primary;
    }
  }
}

.nuxt-link-exact-active {
  border-bottom: 2px solid $color-primary;

  @include respond(md) {
    border-bottom: 1px solid rgba(255, 255, 255, 0.5);
  }
}
</style>
