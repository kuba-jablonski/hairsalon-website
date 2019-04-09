<template functional>
  <div class="container">
    <section class="services">
      <div class="services__heading">
        <h2>Our Services</h2>
        <p>The House of Hair Salon & Spa, incididunt ut labore et dolore magna aliqua.</p>
      </div>
      <div class="services__cards">
        <div class="card">
          <img src="~/assets/images/s1.png">
          <h4>Coloring</h4>
          <p>Ut enim ad minim veniam, quis trud exercitation...</p>
        </div>
        <div class="card">
          <img src="~/assets/images/s3.png">
          <h4>Haircut</h4>
          <p>Consectetur adipisicing elit, sed doe eiusmod.</p>
        </div>
        <div class="card">
          <img src="~/assets/images/s4.png">
          <h4>Hairstyle</h4>
          <p>Nemo enim ipsam voluptatem quia voluptas</p>
        </div>
        <div class="card">
          <img src="~/assets/images/s3.png">
          <h4>Coloring</h4>
          <p>Ut enim ad minim veniam, quis trud exercitation...</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.services {
  text-align: center;
  background-color: #fff;

  &__heading {
    margin-bottom: 5rem;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 2rem;

    @include respond(md) {
      grid-template-columns: repeat(2, 1fr);
    }

    @include respond(xs) {
      grid-template-columns: 1fr;
    }
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
