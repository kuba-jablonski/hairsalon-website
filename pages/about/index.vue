<template>
  <div>
    <page-header>
      About Us
      <template v-slot:link>
        About
      </template>
    </page-header>
    <div class="container">
      <div class="about">
        <div class="about__title">
          <div class="about__title-bg">
            History
          </div>
          <p>New York &middot; Since 2004</p>
          <h2>About Our Stories</h2>
        </div>
        <p class="about__text">
          At Hairone Salon, we are lorem ipsum dolor sit amet, consectetur adipi elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
      </div>
    </div>
    <div class="video">
      <div class="container">
        <div class="video__card">
          <img
            class="video__img"
            src="~/assets/images/44.jpg"
          >
          <button class="video__btn">
            Play
          </button>
        </div>
        <div class="data">
          <div class="display">
            <div class="display__bg">
              Case
            </div>
            <div class="display__number">
              457
            </div>
            <div class="display__name">
              projects completed
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Client
            </div>
            <div class="display__number">
              343
            </div>
            <div class="display__name">
              happy customers
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Award
            </div>
            <div class="display__number">
              379
            </div>
            <div class="display__name">
              award winners
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Style
            </div>
            <div class="display__number">
              97
            </div>
            <div class="display__name">
              different hairstyles
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PageHeader from '~/components/Shared/PageHeader/PageHeader'

export default {
  components: {
    PageHeader
  }
}
</script>

<style lang="scss" scoped>
.display {
  position: relative;

  &__bg {
    font-family: $font-display;
    font-size: 5rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    display: flex;
    justify-content: center;
  }

  &__number {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 5.1rem;
  }

  &__name {
    position: absolute;
    bottom: -2rem;
    left: 50%;
    width: 100%;
    transform: translateX(-50%);
    text-align: center;
    text-transform: uppercase;
    font-size: 1.2rem;
    color: $color-font-light;
  }
}

.data {
  position: relative;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 3rem;
  padding-bottom: 8rem;
  z-index: 1;
}

.video {
  position: relative;

  &::before {
    position: absolute;
    bottom: 0;
    right: 0;
    content: '';
    height: 60%;
    background-color: #f6f9f9;
    width: 100%;
  }

  &__card {
    position: relative;
    box-shadow: 2px 4px 10px rgba(black, 0.1);
    padding: 2rem;
    margin-bottom: 8rem;
    background-color: white;
  }

  &__img {
    width: 100%;
    display: block;
  }

  &__btn {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 8rem;
    height: 8rem;
    border-radius: 50%;
    background-color: $color-primary;
    border: none;
    outline: none;
    cursor: pointer;
  }
}

.about {
  display: grid;
  grid-template-columns: 3fr 4fr;
  grid-gap: 8rem;
  align-items: start;
  padding-bottom: 8rem;

  &__title {
    position: relative;

    p {
      position: absolute;
      top: 10%;
      right: 0;
      margin: 0;
    }

    h2 {
      position: absolute;
      bottom: 0;
      right: 0;
      margin: 0;
    }
  }

  &__title-bg {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    display: flex;
    justify-content: flex-end;
  }

  &__text {
    color: $color-font-dark;
    font-style: italic;
    font-size: 2rem;
  }
}
</style>
