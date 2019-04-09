<template functional>
  <div class="container">
    <section class="about">
      <span class="about__bgtext">
        about<br>us
      </span>
      <div class="about__titlebox">
        <h2>Hair Salon</h2>
        <p>The House of Hair Salon & Spa</p>
      </div>
      <img
        class="about__img"
        src="~/assets/images/15.jpg"
        alt=""
      >
      <div class="about__details">
        <h3>Beautiful Hair Comes From A Legendary.</h3>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam laboriosam molestias, magni, saepe ducimus doloribus animi corporis illo, corrupti reprehenderit modi natus.</p>
        <base-button
          primary
          class="about__btn"
        >
          Read More
        </base-button>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.about {
  background: white;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 2rem;
  align-items: center;
  border-bottom: 1px solid #e6e6e6;

  @include respond(md) {
    grid-template-columns: 1fr 1fr;
    grid-gap: 4rem;
  }

  @include respond(sm) {
    grid-template-columns: 100%;
  }

  &__bgtext {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    grid-column: 1/1;
    grid-row: 1/1;

    @include respond(lg) {
      font-size: 7rem;

      br {
        display: none;
      }
    }
  }

  &__titlebox {
    position: relative;
    z-index: 1;
    grid-column: 1/1;
    grid-row: 1/1;
  }

  &__img {
    display: block;
    width: 35rem;
    box-shadow: 0 2px 40px 8px rgba(15, 15, 15, 0.15);
    justify-self: center;

    @include respond(sm) {
      max-width: 100%;
      width: 50rem;
    }
  }

  &__details {
    @include respond(md) {
      grid-column: span 2;
    }
    @include respond(sm) {
      grid-column: span 1;
    }
  }

  &__btn {
    margin-top: 4rem;
  }
}
</style>
