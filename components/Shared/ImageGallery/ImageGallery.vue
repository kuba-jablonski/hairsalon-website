<template>
  <div>
    <div class="control">
      <button
        v-for="control in controls"
        :key="control.display"
        class="control__btn"
        :class="{'control__btn--active': activeCategory === control.display }"
        @click="filter(control)"
      >
        {{ control.display }}
      </button>
    </div>
    <div
      ref="grid"
      class="grid"
    >
      <div
        v-for="(item, index) in items"
        :key="item.img"
        :class="item.classes"
      >
        <div :class="{'aspect': true, 'aspect__active': square}">
          <div class="overlay">
            <h3 class="overlay__heading">
              Hairstyle
            </h3>
            <p class="overlay__text">
              Lorem ipsum dolor sit amet.
            </p>
            <div @click="openModal(index)">
              <search-icon class="overlay__icon" />
            </div>
          </div>
          <div :class="{'aspect__inner': square}">
            <img
              class="img"
              :src="item.img"
            >
          </div>
        </div>
      </div>
    </div>
    <image-gallery-modal
      :show="modalOpen"
      :active-item-index="activeItemIndex"
      :items="items"
      @close="modalOpen = false"
      @changeIndex="changeIndex($event)"
    />
  </div>
</template>

<script>
import imagesLoaded from 'imagesloaded'
import SearchIcon from '~/assets/images/search.svg?inline'
import ImageGalleryModal from '~/components/Shared/ImageGallery/ImageGalleryModal'

export default {
  components: {
    SearchIcon,
    ImageGalleryModal
  },
  props: {
    controls: {
      type: Array,
      required: true
    },
    items: {
      type: Array,
      required: true
    },
    square: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      activeCategory: 'All',
      activeItemIndex: 0,
      modalOpen: false
    }
  },
  mounted() {
    if (process.browser) {
      const Isotope = require('isotope-layout')
      const grid = this.$refs.grid

      this.iso = new Isotope(grid, {
        itemSelector: '.grid__item'
      })

      imagesLoaded(grid).on('progress', () => {
        this.iso.layout()
      })
    }
  },
  methods: {
    filter(target) {
      this.iso.arrange({
        filter: target.selector
      })
      this.activeCategory = target.display
    },
    openModal(index) {
      this.activeItemIndex = index
      this.modalOpen = true
    },
    changeIndex(newIndex) {
      if (newIndex > this.items.length - 1) {
        newIndex = 0
      }
      if (newIndex < 0) {
        newIndex = this.items.length - 1
      }
      this.activeItemIndex = newIndex
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
    padding: 1rem;

    &:hover .overlay {
      opacity: 1;
    }

    &:hover img {
      transform: scale(1.2);
    }

    &--x4 {
      width: 25%;
    }

    &--x3 {
      width: 33%;
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
  transition: opacity 0.5s;

  &__heading {
    color: $color-primary;
    font-size: 2.5rem;
    font-weight: bold;
  }

  &__text {
    color: white;
  }

  &__icon {
    height: 2.5rem;
    width: 2.5rem;
    fill: white;
    position: absolute;
    left: 50%;
    bottom: 2rem;
    transform: translateX(-50%);
    cursor: pointer;
    transition: all 0.2s;

    &:hover {
      fill: $color-primary;
    }
  }
}

.img {
  width: 100%;
  height: 100%;
  transition: transform 0.4s;
}

.aspect {
  position: relative;
  width: 100%;
  overflow: hidden;

  &__active {
    height: 0;
    padding-bottom: 100%;
  }

  &__inner {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
}
</style>
