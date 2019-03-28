<template>
  <section class="booking">
    <div class="container">
      <div class="booking__content">
        <div class="booking__text">
          <h2>Make Stilo Your Number One Choice</h2>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo, ipsa. Officiis exercitationem sit non dicta?</p>
          <div class="booking__cta">
            <base-button primary>
              Book an appointment
            </base-button>
            <base-button>contact us</base-button>
          </div>
        </div>
        <img src="~/assets/images/cta.png">
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.booking {
  padding: 0;
  background-color: red;

  &__content {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  &__text {
    margin-top: 8rem;
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
