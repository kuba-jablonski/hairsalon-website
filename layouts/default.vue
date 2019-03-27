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
    <div class="container">
      <footer class="footer">
        <div class="footer__copy">
          <img
            class="footer__logo"
            src="~/assets/images/logo.png"
            alt="Akame"
          >
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quam accusantium esse repellendus cupiditate asperiores neque dicta repudiandae atque reiciendis.</p>
          <p>Copyright &copy;2019 All rights reserved</p>
        </div>
        <div class="footer__opening">
          <h3>Opening Times</h3>
          <p>Monday - Friday: 10.00 - 23.00</p>
          <p>Saturday: 10.00 - 19.00</p>
          <div class="footer__social">
            <div class="footer__icon-bg">
              <check-icon class="footer__icon" />
            </div>
          </div>
        </div>
        <div class="footer__contact">
          <h3>Contact Us</h3>
          <p>Tel: 000 111 222</p>
          <p>E-mail: test@example.com</p>
          <p>Address: 2880 Kessla Way</p>
        </div>
      </footer>
    </div>
  </div>
</template>

<script>
import CheckIcon from '~/assets/images/check.svg?inline'

export default {
  components: {
    CheckIcon
  }
}
</script>


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

.footer {
  padding: 8rem 0;
  background-color: #d8d8d8;
  display: grid;
  grid-template-columns: repeat(3, 1fr);

  &__opening p:last-of-type {
    margin-bottom: 2rem;
  }

  &__logo {
    display: block;
    margin-bottom: 2rem;
    height: 3.84rem;
  }

  &__copy p:first-of-type {
    margin-bottom: 2rem;
  }

  &__social {
    display: flex;
  }

  &__icon-bg {
    height: 4rem;
    width: 4rem;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
  }

  &__icon {
    height: 2rem;
    width: 2rem;
    fill: red;
  }
}

.nuxt-link-exact-active {
  border-bottom: 2px solid $color-primary;
}
</style>
