<template functional>
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
</template>

<style lang="scss" scoped>
.about {
  background: white;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  // padding: 8rem 0;
  align-items: center;
  border-bottom: 1px solid #e6e6e6;

  &__bgtext {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    grid-column: 1/1;
    grid-row: 1/1;
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
  }

  &__details {
    margin-left: 2.5rem;
  }

  &__btn {
    margin-top: 4rem;
  }
}
</style>
