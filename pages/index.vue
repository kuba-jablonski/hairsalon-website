<template>
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
        <section>
          <h2>Our Services</h2>
          <p>The House of Hair Salon & Spa, incididunt ut labore et dolore magna aliqua.</p>
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
        </section>
      </div>
    </main>
  </div>
</template>

<style lang="scss" scoped>
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
  padding: 5rem 0;
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
