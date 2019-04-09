<template functional>
  <div class="header__background">
    <div class="container">
      <header class="header">
        <div class="header__textbox">
          <h1 class="header__heading">
            We care about <br> your hair
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
</template>

<style lang="scss" scoped>
.header {
  height: 100%;
  display: flex;
  align-items: center;

  &__background {
    height: calc(100vh - 10rem);
    background-image: url('~assets/images/16.jpg');
    background-position: center;
    background-size: cover;
  }

  &__heading {
    font-size: 7.2rem;
    line-height: 1.2;
    text-transform: capitalize;
    margin-bottom: 4rem;
    font-weight: 300;

    @include respond(md) {
      font-size: 6rem;
    }

    @include respond(xs) {
      font-size: 3.6rem;
    }
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
</style>
