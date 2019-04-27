<template>
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
        <h4>Opening Times</h4>
        <p>Monday - Friday: 10.00 - 23.00</p>
        <p>Saturday: 10.00 - 19.00</p>
        <div class="footer__social">
          <div class="footer__icon-bg footer__icon-bg--facebook">
            <icon-facebook class="footer__icon" />
          </div>
          <div class="footer__icon-bg footer__icon-bg--twitter">
            <icon-twitter class="footer__icon" />
          </div>
          <div class="footer__icon-bg footer__icon-bg--google">
            <icon-google class="footer__icon" />
          </div>
          <div class="footer__icon-bg footer__icon-bg--instagram">
            <icon-instagram class="footer__icon" />
          </div>
        </div>
      </div>
      <div class="footer__contact">
        <h4>Contact Us</h4>
        <p>Tel: 000 111 222</p>
        <p>E-mail: test@example.com</p>
        <p>Address: 2880 Kessla Way</p>
      </div>
    </footer>
  </div>
</template>

<script>
import IconFacebook from '~/assets/images/facebook.svg?inline'
import IconTwitter from '~/assets/images/twitter.svg?inline'
import IconGoogle from '~/assets/images/google-plus.svg?inline'
import IconInstagram from '~/assets/images/instagram.svg?inline'

export default {
  components: {
    IconFacebook,
    IconTwitter,
    IconGoogle,
    IconInstagram
  }
}
</script>

<style lang="scss" scoped>
.footer {
  padding: 8rem 0;
  display: grid;
  grid-gap: 3rem;
  grid-template-columns: 4fr 3fr 3fr;

  &__opening p:last-of-type {
    margin-bottom: 2rem;
  }

  &__logo {
    display: block;
    margin-bottom: 2rem;
    height: 2rem;
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
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    transition: all 0.3s;
    cursor: pointer;

    &--facebook {
      background-color: #4b62b3;
    }

    &--twitter {
      background-color: #03baeb;
    }

    &--google {
      background-color: #cb242e;
    }

    &--instagram {
      background-color: #057ad7;
    }

    &:hover {
      background-color: $color-primary;
    }

    &:not(:last-child) {
      margin-right: 1.8rem;
    }
  }

  &__icon {
    height: 2rem;
    width: 2rem;
    fill: white;
  }
}
</style>
