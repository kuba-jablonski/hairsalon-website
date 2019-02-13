<template>
  <div>
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
        <base-button class="nav__cta">
          Book Now
        </base-button>
      </nav>
    </div>
    <nuxt />
  </div>
</template>

<style lang="scss" scoped>
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
  }

  &__cta {
    margin-left: 5rem;
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
}
</style>
