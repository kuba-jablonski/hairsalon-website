<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
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
      </div>
    </section>
  </div>
</template>

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
}

.grid-item-1 {
  grid-column: span 1;
  grid-row: span 1;
}

.grid-item-2 {
  grid-column: span 2;
  grid-row: span 2;
}

.work {
  background: white;

  &__heading {
    text-align: center;
  }
}
</style>
