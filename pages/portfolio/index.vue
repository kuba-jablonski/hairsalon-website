<template>
  <div class="container">
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
        <div class="aspect">
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
          <div class="aspect__inner">
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
import img4 from '~/assets/images/4.jpg'
import img6 from '~/assets/images/6.jpg'
import img8 from '~/assets/images/8.jpg'
import img9 from '~/assets/images/9.jpg'
import img18 from '~/assets/images/18.jpg'
import img19 from '~/assets/images/19.jpg'
import img21 from '~/assets/images/21.jpg'
import img22 from '~/assets/images/22.jpg'
import img23 from '~/assets/images/23.jpg'
import img25 from '~/assets/images/25.jpg'
import img26 from '~/assets/images/26.jpg'
import img29 from '~/assets/images/29.jpg'

export default {
  components: {
    SearchIcon,
    ImageGalleryModal
  },
  data() {
    return {
      activeCategory: 'All',
      activeItemIndex: 0,
      modalOpen: false,
      controls: [
        { display: 'All', selector: '*' },
        { display: 'Haircuts', selector: '.haircuts' },
        { display: 'Coloring', selector: '.coloring' },
        { display: 'Barber', selector: '.barber' },
        { display: 'Shaving', selector: '.shaving' },
        { display: 'Hairstyle', selector: '.hairstyle' },
        { display: 'Massages', selector: '.massages' }
      ],
      items: [
        { img: img18, classes: ['grid__item', 'haircuts'] },
        { img: img19, classes: ['grid__item', 'haircuts'] },
        { img: img6, classes: ['grid__item', 'coloring'] },
        { img: img4, classes: ['grid__item', 'massages'] },
        { img: img8, classes: ['grid__item', 'shaving'] },
        { img: img9, classes: ['grid__item', 'hairstyle'] },
        { img: img21, classes: ['grid__item', 'coloring'] },
        { img: img22, classes: ['grid__item', 'barber'] },
        { img: img23, classes: ['grid__item', 'barber'] },
        { img: img25, classes: ['grid__item', 'shaving'] },
        { img: img26, classes: ['grid__item', 'hairstyle'] },
        { img: img29, classes: ['grid__item', 'massages'] }
      ]
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
    width: 33%;
    padding: 1rem;

    &:hover .overlay {
      opacity: 1;
    }

    &:hover .img {
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
  display: block;
}

.aspect {
  position: relative;
  width: 100%;
  // height: 0;
  // padding-bottom: 100%;
  overflow: hidden;

  // &__inner {
  //   position: absolute;
  //   top: 0;
  //   right: 0;
  //   bottom: 0;
  //   left: 0;
  // }
}
</style>
