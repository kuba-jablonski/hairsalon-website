<template>
  <div>
    <div class="container">
      <nav class="nav">
        <div class="nav__brand">
          Akame
        </div>
        <ul class="nav__items">
          <li class="nav__item">
            Home
          </li>
          <li class="nav__item">
            Portfolio
          </li>
          <li class="nav__item">
            Services
          </li>
          <li class="nav__item">
            About Us
          </li>
          <li class="nav__item">
            Blog
          </li>
          <li class="nav__item">
            Contact
          </li>
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

  &__brand {
    margin-right: auto;
  }

  &__items {
    display: flex;
  }

  &__cta {
    margin-left: 5rem;
  }
}
</style>
