<template>
  <div>
    <div class="control">
      <button
        v-for="control in controls"
        :key="control.display"
        class="control__btn"
        :class="{'control__btn--active': activeItem === control.display }"
        @click="filter(control)"
      >
        {{ control.display }}
      </button>
    </div>
    <div class="grid">
      <div
        v-for="item in items"
        :key="item.img"
        :class="item.classes"
      >
        <div class="aspect">
          <div class="overlay">
            <h3 class="overlay__heading">
              Hairstyle
            </h3>
            <p class="overlay__text">
              Lorem ipsum dolor sit amet.
            </p>
            <search-icon class="overlay__icon" />
          </div>
          <div class="aspect__inner">
            <img
              class="img"
              :src="item.img"
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SearchIcon from '~/assets/images/search.svg?inline'

let iso

export default {
  components: {
    SearchIcon
  },
  props: {
    controls: {
      type: Array,
      required: true
    },
    items: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      activeItem: 'All'
    }
  },
  mounted() {
    if (process.browser) {
      const Isotope = require('isotope-layout')
      iso = new Isotope('.grid', {
        itemSelector: '.grid__item'
      })
    }
  },
  methods: {
    filter(target) {
      iso.arrange({
        filter: target.selector
      })
      this.activeItem = target.display
    }
  }
}
</script>

<style lang="scss" scoped>
.control {
  display: flex;
  justify-content: center;
  flex-flow: row wrap;

  &__btn {
    border: none;
    outline: none;
    font: inherit;
    background-color: white;
    padding: 0.5rem 1rem;
    cursor: pointer;
    margin-bottom: 2rem;

    &:not(:last-child) {
      margin-right: 3rem;

      @include respond(sm) {
        margin-right: 2rem;
      }
    }

    @include respond(sm) {
      font-size: 1.4rem;
    }

    @include respond(xs) {
      font-size: 1.2rem;
    }

    &--active {
      border-bottom: 2px solid $color-primary;
      color: $color-primary;
    }
  }
}

.grid {
  margin: 0 -1rem 4rem -1rem;

  &__item {
    width: 25%;
    padding: 1rem;

    &:hover .overlay {
      opacity: 1;
    }

    &:hover img {
      transform: scale(1.2);
    }

    @include respond(md) {
      width: 50%;
    }

    @include respond(xs) {
      width: 100%;
    }

    &--lgl {
      width: 50%;

      @include respond(xs) {
        width: 100%;
      }
    }

    &--lgs {
      @include respond(md) {
        width: 100%;
      }
    }
  }
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.2s;

  &__heading {
    color: $color-primary;
    font-size: 2.5rem;
    font-weight: bold;
  }

  &__text {
    color: white;
  }

  &__icon {
    height: 2rem;
    width: 2rem;
    fill: white;
    position: absolute;
    left: 50%;
    bottom: 2rem;
    transform: translateX(-50%);
  }
}

.img {
  width: 100%;
  height: 100%;
  transition: transform 0.2s;
}

.aspect {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  overflow: hidden;

  &__inner {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
}
</style>
