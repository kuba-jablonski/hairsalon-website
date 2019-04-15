<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
      <div class="work__controls">
        <button
          class="work__control"
          :class="{active: activeItem === 'all'}"
          @click="filter({ name: 'all', selector: '*'})"
        >
          All
        </button>
        <button
          class="work__control"
          :class="{active: activeItem === 'haircuts'}"
          @click="filter({ name: 'haircuts', selector: '.haircuts'})"
        >
          Haircuts
        </button>
        <button
          class="work__control"
          :class="{active: activeItem === 'dye'}"
          @click="filter({ name: 'dye', selector: '.dye' })"
        >
          Dye
        </button>
        <button
          class="work__control"
          :class="{active: activeItem === 'shave'}"
          @click="filter({ name: 'shave', selector: '.shave' })"
        >
          Shave
        </button>
        <button
          class="work__control"
          :class="{active: activeItem === 'hairstyle'}"
          @click="filter({ name: 'hairstyle', selector: '.hairstyle' })"
        >
          Hairstyle
        </button>
      </div>
      <div class="image-grid">
        <div class="grid-item haircuts">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/5.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item dye grid-item-2">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/1.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item shave grid-item-3">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/7.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item hairstyle">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/8.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item dye">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/9.jpg">
            </div>
          </div>
        </div>
      </div>
      <div class="work__cta">
        <base-button>
          View all work
        </base-button>
      </div>
    </section>
  </div>
</template>

<script>
let iso

export default {
  data() {
    return {
      activeItem: null
    }
  },
  mounted() {
    if (process.browser) {
      const Isotope = require('isotope-layout')
      const elem = document.querySelector('.image-grid')
      iso = new Isotope(elem, {
        itemSelector: '.grid-item'
      })
      // eslint-disable-next-line no-console
    }
  },
  methods: {
    filter(target) {
      iso.arrange({
        filter: target.selector
      })
      this.activeItem = target.name
    }
  }
}
</script>


<style lang="scss" scoped>
.work {
  &__heading {
    text-align: center;
    margin-bottom: 4rem;
  }

  &__controls {
    display: flex;
    justify-content: center;
  }

  &__control {
    border: none;
    outline: none;
    font: inherit;
    background-color: white;
    padding: 0.5rem 1rem;
    cursor: pointer;
    margin-bottom: 2rem;

    &:not(:last-child) {
      margin-right: 3rem;
    }
  }
}

.active {
  border-bottom: 2px solid $color-primary;
  color: $color-primary;
}

.grid-item {
  width: 25%;
  padding: 1rem;

  @include respond(md) {
    width: 50%;
  }

  @include respond(xs) {
    width: 100%;
  }
}

.grid-item-2 {
  width: 50%;

  @include respond(xs) {
    width: 100%;
  }
}

.grid-item-3 {
  @include respond(md) {
    width: 100%;
  }
}

img {
  width: 100%;
  height: 100%;
}

.aspect {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  overflow: hidden;
}

.aspect__inner {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

/* Add more aspect ratios here */
.aspect--16x9 {
  padding-bottom: 56.25%;
}
</style>
