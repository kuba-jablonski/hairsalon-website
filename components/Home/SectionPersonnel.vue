<template>
  <div>
    <section class="personnel">
      <div class="thumbnail" />
      <div class="container">
        <div class="personnel__top">
          <div class="personnel__text">
            <h2>Our Experts</h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis nostrud exercitation ullamco laboris nisi ut aliquip ex.
            </p>
            <div class="personnel__cert">
              <img src="~/assets/images/certificate-1.webp">
              <img src="~/assets/images/certificate-2.webp">
              <img src="~/assets/images/certificate-3.webp">
            </div>
          </div>
        </div>

        <div class="personnel__cards">
          <div class="personnel__card">
            <img src="~/assets/images/10.jpg">
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/11.jpg">
            <div class="personnel__card-text">
              <h4>Teigan Duran</h4>
              <p>Stylist</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/12.jpg">
            <div class="personnel__card-text">
              <h4>Tanya Ramsey</h4>
              <p>Hairstylist</p>
            </div>
          </div>
          <div class="personnel__card">
            <img src="~/assets/images/13.jpg">
            <div class="personnel__card-text">
              <h4>Donna Carr</h4>
              <p>Barber</p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="container">
      <div class="section-break" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.section-break {
  border-bottom: 1px solid #e6e6e6;
}
.thumbnail {
  background-image: url('~assets/images/14.png');
  position: absolute;
  width: 55.5rem;
  height: 70%;
  top: 0;
  right: 50%;
  z-index: -1;
}

.personnel {
  position: relative;
  z-index: 1;

  &::before {
    position: absolute;
    width: 100%;
    height: 70%;
    content: '';
    top: 0;
    right: 0;
    background-color: #f6f9f9;
    z-index: -1;
  }

  &__top {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 2rem;
  }

  &__text {
    grid-column: 2;
    z-index: 1;

    p {
      margin-bottom: 4rem;
    }
  }

  &__cert {
    margin-bottom: 4rem;

    & > * {
      margin-right: 2rem;
    }
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 3rem;

    img {
      width: 100%;
      filter: grayscale(1);

      &:hover {
        filter: none;
      }
    }
  }

  &__card {
    border: 1px solid #e5e5e5;
  }

  &__card-text {
    padding: 2rem;
  }
}
</style>
