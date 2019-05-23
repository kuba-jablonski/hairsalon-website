<template>
  <nav class="nav">
    <div class="container">
      <div class="nav__content">
        <img
          class="nav__logo"
          src="~/assets/images/logo.png"
          alt="Akame"
        >
        <ul class="nav__items">
          <li
            v-for="item in items"
            :key="item.link"
          >
            <nuxt-link
              :to="item.link"
              class="nav__item"
            >
              {{ item.display }}
            </nuxt-link>
          </li>
        </ul>
        <button
          class="menu-btn"
          @click="navOpen = !navOpen"
        >
          <icon-menu class="menu-btn__icon" />
        </button>
        <base-button class="nav__cta">
          Book Now
        </base-button>
        <layout-nav-mobile
          :show="navOpen"
          :items="items"
          @close="navOpen = false"
        />
      </div>
    </div>
  </nav>
</template>

<script>
import IconMenu from '~/assets/images/menu.svg?inline'
import LayoutNavMobile from './LayoutNavMobile'

export default {
  components: {
    IconMenu,
    LayoutNavMobile
  },
  data() {
    return {
      navOpen: false,
      items: [
        { display: 'Home', link: '/' },
        { display: 'Portfolio', link: '/portfolio' },
        { display: 'Services', link: '/services' },
        { display: 'About Us', link: '/about' },
        { display: 'Blog', link: '/blog' },
        { display: 'Contact', link: '/contact' }
      ]
    }
  }
}
</script>


<style lang="scss" scoped>
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

.nav {
  background-color: #fff;
  border-bottom: 1px solid $color-grey-light-1;

  &__content {
    display: flex;
    align-items: center;
    height: 10rem;

    @include respond(md) {
      height: 6rem;
    }
  }

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
