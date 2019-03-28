<template>
  <section class="news">
    <div class="container">
      <div class="news__heading">
        <h2>Latest News</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, facere?</p>
      </div>
      <div class="news__cards">
        <div class="news__card">
          <img src="~/assets/images/10.jpg">
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
        <div class="news__card">
          <img src="~/assets/images/10.jpg">
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
        <div class="news__card">
          <img src="~/assets/images/10.jpg">
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.news {
  &__heading {
    text-align: center;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 2rem;
  }

  &__card {
    img {
      width: 100%;
    }
  }
}
</style>
