<template>
  <section class="personnel">
    <div class="personnel__wrapper">
      <div class="container">
        <div class="personnel__one">
          <img
            class="personnel__bgimage"
            src="~/assets/images/14.png"
          >
          <div class="personnel__text">
            <h2>Our Experts</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Porro eos ea vel debitis ad, officiis natus maiores consequatur. Ea, nesciunt.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="personnel__two">
      <div class="container">
        <div class="personnel__cards">
          <div class="personnel__card">
            <img src="~/assets/images/10.jpg">
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/10.jpg">
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/10.jpg">
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/10.jpg">
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- <div class="personnel__wrapper">
    <div class="container">
      <section class="personnel" />

    </div>
  </div> -->
</template>

<style lang="scss" scoped>
.personnel {
  padding-top: 0;
  // display: grid;
  // grid-template-columns: 1fr 1fr;
  // grid-gap: 5rem;

  &__one {
    // background-color: #f6f9f9;
    background-color: red;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 5rem;
  }

  &__two {
    // transform: translateY(-50%);
  }

  &__wrapper {
    // background-color: #f6f9f9;
    background-color: black;
  }

  &__bgimage {
    display: block;
  }

  &__text {
    margin-top: 8rem;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 2rem;
  }

  &__card {
    border: 1px solid black;

    img {
      width: 100%;
      display: block;
    }
  }
}
</style>
