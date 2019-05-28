<template>
  <div>
    <page-header>
      Our Services
      <template v-slot:link>
        Services
      </template>
    </page-header>
    <div class="service">
      <div class="service__card">
        <div class="service__details">
          <h2>Hair Cuts & Style</h2>
          <p>
            <span>Women's Haircut:</span>
            <span class="service__price">
              $55+
            </span>
          </p>
          <p>
            <span>Men's Haircut:</span>
            <span class="service__price">
              $75+
            </span>
          </p>
          <p>
            <span>Up Do Style:</span>
            <span class="service__price">
              $35+
            </span>
          </p>
          <p>
            <span>Half-up do style:</span>
            <span class="service__price">
              $45+
            </span>
          </p>
        </div>
      </div>
      <div class="jarallax">
        <img
          class="jarallax-img"
          src="~/assets/images/30.jpg"
          alt=""
        >
      </div>
    </div>
    <div class="service">
      <div class="jarallax">
        <img
          class="jarallax-img"
          src="~/assets/images/31.jpg"
          alt=""
        >
      </div>
      <div class="service__card">
        <div class="service__details">
          <h2>Hair dyed</h2>
          <p>
            <span>Dye L'Oréal:</span>
            <span class="service__price">
              $55+
            </span>
          </p>
          <p>
            <span>Dye Davines:</span>
            <span class="service__price">
              $75+
            </span>
          </p>
          <p>
            <span>Dye GolDWell:</span>
            <span class="service__price">
              $35+
            </span>
          </p>
          <p>
            <span>Dye Oriental:</span>
            <span class="service__price">
              $45+
            </span>
          </p>
        </div>
      </div>
    </div>
    <div class="service">
      <div class="service__card">
        <div class="service__details">
          <h2>Hair Care</h2>
          <p>
            <span>Shampoo & Blow Dry:</span>
            <span class="service__price">
              $55+
            </span>
          </p>
          <p>
            <span>Personalized Color:</span>
            <span class="service__price">
              $75+
            </span>
          </p>
          <p>
            <span> Formal Styling:</span>
            <span class="service__price">
              $35+
            </span>
          </p>
          <p>
            <span>Bridal & Wedding:</span>
            <span class="service__price">
              $45+
            </span>
          </p>
        </div>
      </div>
      <div class="jarallax">
        <img
          class="jarallax-img"
          src="~/assets/images/32.jpg"
          alt=""
        >
      </div>
    </div>
  </div>
</template>

<script>
import PageHeader from '~/components/Shared/PageHeader/PageHeader'

export default {
  components: {
    PageHeader
  },
  mounted() {
    if (process.browser) {
      const jarallax = require('jarallax').jarallax
      jarallax(document.querySelectorAll('.jarallax'), {
        speed: 0.3
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.service {
  display: grid;
  grid-template-columns: 1fr 1fr;

  &:first-of-type {
    border-top: 1px solid #e5e5e5;
  }

  &:last-of-type {
    border-bottom: 1px solid #e5e5e5;
  }

  &__card {
    height: 50rem;
    display: flex;
    align-items: center;

    @include respond(md) {
      grid-column: span 2;
    }
  }

  &__details {
    width: 100%;

    padding-left: 2rem;

    h2 {
      margin-bottom: 4rem;
    }

    p {
      margin-bottom: 3rem;
      max-width: 25rem;
      display: flex;
      justify-content: space-between;
    }

    @media screen and (max-width: 1160px) {
      margin-left: 0;
    }
  }

  &__price {
    font-weight: bold;
    color: #252525;
  }
}

.jarallax {
  position: relative;
  z-index: 0;

  @include respond(md) {
    display: none;
  }
}
.jarallax > .jarallax-img {
  position: absolute;
  object-fit: cover;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>
