<template>
  <div>
    <page-header>
      About Us
      <template v-slot:link>
        About
      </template>
    </page-header>
    <div class="container">
      <section class="about">
        <div class="title">
          <div class="title__bg">
            History
          </div>

          <p>New York &middot; Since 2004</p>
          <h2>About Our Stories</h2>
        </div>
        <p class="text">
          At Hairone Salon, we are lorem ipsum dolor sit amet, consectetur adipi elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
      </section>
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
.title {
  position: relative;

  &__bg {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    display: flex;
    justify-content: flex-end;
  }

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

.text {
  color: #252525;
  font-style: italic;
  font-size: 2rem;
}

.about {
  display: grid;
  grid-template-columns: 3fr 4fr;
  grid-gap: 8rem;
  align-items: center;
  border-bottom: 1px solid #e6e6e6;
  align-items: start;

  &__bgtext {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    grid-column: 1/1;
    grid-row: 1/1;
    display: flex;
    justify-content: flex-end;

    @include respond(lg) {
      font-size: 7rem;
    }
  }

  &__titlebox {
    position: relative;
    z-index: 1;
    grid-column: 1/1;
    grid-row: 1/1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-end;
    height: 100%;

    h2,
    p {
      margin: 0;
    }
  }
}
</style>
