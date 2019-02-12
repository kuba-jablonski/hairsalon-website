<template>
  <div class="bg-image">
    <div class="container">
      <header class="header">
        <div class="header__textbox">
          <h1>We care about your hair</h1>
          <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Iure itaque quasi esse autem rerum necessitatibus doloremque at deserunt voluptate commodi cumque numquam, delectus tenetur similique. Excepturi id explicabo quod blanditiis.</p>
          <base-button>About Us</base-button>
        </div>
      </header>
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
            <div>
              <h3>Beautiful Hair Comes From A Legendary.</h3>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam laboriosam molestias, magni, saepe ducimus doloribus animi corporis illo, corrupti reprehenderit modi natus. Nisi, sequi eos dolorem consectetur error vero? Aspernatur.</p>
              <base-button>Read More</base-button>
            </div>
          </section>
          <section>
            Hello
          </section>
        </div>
      </main>
    </div>
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
    font-size: 8rem;
    text-transform: uppercase;
    line-height: 1;
    color: #f7f7f7;
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
    height: 30rem;
  }
}
</style>
