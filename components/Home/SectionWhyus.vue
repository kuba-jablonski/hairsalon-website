<template>
  <div class="whyus__wrapper">
    <div class="container">
      <section class="whyus">
        <div class="whyus__thumbnail">
          <img
            class="whyus__img"
            src="~/assets/images/4.jpg"
          >
        </div>
        <div>
          <div class="whyus__heading">
            <h2>Why Choose Us</h2>
            <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
          </div>
          <ul>
            <li class="whyus__list-item">
              <check-icon class="whyus__list-item-icon" />
              We Strive For LIVE Answer On Our Calls.
            </li>
            <li class="whyus__list-item">
              <check-icon class="whyus__list-item-icon" />
              A Wide Spectrum Of Skills And Experience.
            </li>
            <li class="whyus__list-item">
              <check-icon class="whyus__list-item-icon" />
              Fast Response To Requests & Critical Response Time Guaranteed.
            </li>
            <li class="whyus__list-item">
              <check-icon class="whyus__list-item-icon" />
              We Help Solve Your Business Problems.
            </li>
          </ul>
        </div>
      </section>
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
.whyus {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 4rem;

  &__wrapper {
    background-color: #f6f9f9;
  }

  &__thumbnail {
    height: 38rem;
    background-color: #e6e6e6;
    position: relative;
  }

  &__img {
    position: absolute;
    width: 100%;
    height: 100%;
    top: -3rem;
    left: -3rem;
  }

  &__heading {
    margin-bottom: 5rem;
  }

  &__list-item {
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
  }

  &__list-item-icon {
    margin-right: 1rem;
    fill: $color-primary;
    width: 2rem;
    height: 2rem;
  }
}
</style>
