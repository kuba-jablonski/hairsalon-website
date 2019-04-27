<template>
  <section class="booking">
    <div class="container">
      <div class="booking__content">
        <div class="booking__text">
          <h2>Make Stilo Your <br> Number One Choice</h2>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo, ipsa. Officiis exercitationem sit non dicta?</p>
        </div>
        <div class="booking__cta">
          <base-button primary>
            Book an appointment
          </base-button>
          <base-button>contact us</base-button>
        </div>
      </div>
    </div>
    <div class="bg-image" />
  </section>
</template>

<style lang="scss" scoped>
.bg-image {
  background-image: url('~assets/images/cta.png');
  background-position: center center;
  background-size: cover;
  position: absolute;
  width: 65%;
  top: 0;
  right: 0;
  height: 100%;
  z-index: -1;
  opacity: 0.5;
}

.booking {
  background-color: #f6f9f9;
  position: relative;
  z-index: 1;

  &__content {
  }

  &__text {
    margin-bottom: 4rem;
  }

  &__cta {
    display: flex;
    button:not(:last-child) {
      margin-right: 2rem;
    }
  }

  img {
    width: 100%;
  }
}
</style>
