<template>
  <div>
    <div class="bg-image">
      <div class="container">
        <header class="header">
          <div class="header__textbox">
            <h1 class="header__heading">
              We care about your hair
            </h1>
            <p class="header__text">
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Iure itaque quasi esse autem rerum necessitatibus doloremque at deserunt voluptate commodi cumque numquam, delectus tenetur similique.
            </p>
            <base-button primary>
              About Us
            </base-button>
          </div>
        </header>
      </div>
    </div>
    <main>
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
        <section class="services">
          <div class="services__heading">
            <h2>Our Services</h2>
            <p>The House of Hair Salon & Spa, incididunt ut labore et dolore magna aliqua.</p>
          </div>
          <div class="services__cards">
            <div class="card">
              <img
                src="~/assets/images/s1.png"
                alt=""
              >
              <h4>Coloring</h4>
              <p>Ut enim ad minim veniam, quis trud exercitation...</p>
            </div>
            <div class="card">
              <img
                src="~/assets/images/s3.png"
                alt=""
              >
              <h4>Haircut</h4>
              <p>Consectetur adipisicing elit, sed doe eiusmod.</p>
            </div>
            <div class="card">
              <img
                src="~/assets/images/s4.png"
                alt=""
              >
              <h4>Hairstyle</h4>
              <p>Nemo enim ipsam voluptatem quia voluptas</p>
            </div>
            <div class="card">
              <img
                src="~/assets/images/s3.png"
                alt=""
              >
              <h4>Coloring</h4>
              <p>Ut enim ad minim veniam, quis trud exercitation...</p>
            </div>
          </div>
        </section>
      </div>
      <div class="whyus__wrapper">
        <div class="container">
          <section class="whyus">
            <div class="whyus__thumbnail">
              <img
                class="whyus__img"
                src="~/assets/images/4.jpg"
                alt=""
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
      <div class="container">
        <section class="work">
          <div class="work__heading">
            <h2>Our Work</h2>
            <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
          </div>
          <div class="work__menu">
            <button class="work__menu-item">
              All
            </button>
            <button class="work__menu-item">
              Haircuts
            </button>
            <button class="work__menu-item">
              Dye
            </button>
            <button class="work__menu-item">
              Shave
            </button>
            <button class="work__menu-item">
              Hairstyle
            </button>
          </div>
          <div class="image-grid">
            <img
              class="grid-item"
              src="~/assets/images/5.jpg"
            >
            <img
              class="grid-item grid-item-2"
              src="~/assets/images/1.jpg"
            >
            <img
              class="grid-item"
              src="~/assets/images/7.jpg"
            >
            <img
              class="grid-item"
              src="~/assets/images/8.jpg"
            >
            <img
              class="grid-item"
              src="~/assets/images/9.jpg"
            >
            <!-- <div class="grid-item-1" />
            <div class="grid-item-2" />
            <div class="grid-item" />
            <div class="grid-item" /> -->
          </div>
        </section>
      </div>
    </main>
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
.image-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 24rem);
  grid-gap: 4rem;
}

.grid-item {
  width: 100%;
  height: 100%;
  background-color: black;
  // object-position: right bottom;
}

.grid-item-1 {
  grid-column: span 1;
  grid-row: span 1;
  // height: 100%;
  // width: 100%;
  background-color: black;
}

.grid-item-2 {
  grid-column: span 2;
  grid-row: span 2;
  background-color: black;
}

.bg-image {
  height: calc(100vh - 10rem);
  background-image: url('~assets/images/16.jpg');
  background-position: center;
  background-size: cover;
}

.header {
  height: 100%;
  display: flex;
  align-items: center;

  &__heading {
    font-size: 7.2rem;
    line-height: 1.2;
    text-transform: capitalize;
    margin-bottom: 4rem;
    font-weight: 300;
  }

  &__text {
    margin-bottom: 4rem;
    font-size: 1.8rem;
    line-height: 1.7;
  }

  &__textbox {
    width: 50rem;
  }
}

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

.services {
  text-align: center;
  background-color: #fff;
  // padding: 8rem 0;

  &__heading {
    margin-bottom: 5rem;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 2rem;
  }
}

.whyus {
  // padding: 8rem 0;
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

.work {
  background: white;

  &__heading {
    text-align: center;
  }
}

.card {
  border: 1px solid #e6e6e6;
  padding: 4rem 2rem;

  img {
    margin-bottom: 1.5rem;
  }

  p {
    margin: 0;
  }
}
</style>
