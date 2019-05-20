<template>
  <div class="carousel">
    <transition
      name="slide"
      mode="out-in"
    >
      <div
        :key="activeItemIndex"
        class="carousel__content"
      >
        <div class="carousel__icon">
          &ldquo;
        </div>
        <p class="carousel__quote">
          {{ items[activeItemIndex].quote }}
        </p>
        <div class="carousel__author">
          {{ items[activeItemIndex].author }}
        </div>
      </div>
    </transition>
    <div class="carousel__controls">
      <div
        v-for="number in items.length"
        :key="number"
        :class="{'carousel__control': true, 'carousel__control--active': activeItemIndex === number - 1}"
        @click="changeActiveItem(number - 1)"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeItemIndex: 0,
      items: [
        {
          quote:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusantium, obcaecati iusto. Illum ipsam nisi accusamus eveniet soluta quod sed dicta!',
          author: 'Jarred'
        },
        {
          quote:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusantium, obcaecati iusto. Illum ipsam nisi accusamus eveniet soluta quod sed dicta!',
          author: 'Bob'
        },
        {
          quote:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusantium, obcaecati iusto. Illum ipsam nisi accusamus eveniet soluta quod sed dicta!',
          author: 'Rob'
        }
      ]
    }
  },
  mounted() {
    this.interval = this.activateCarousel()
  },
  methods: {
    activateCarousel() {
      return setInterval(() => {
        if (this.activeItemIndex === this.items.length - 1) {
          this.activeItemIndex = 0
        } else {
          this.activeItemIndex++
        }
      }, 5000)
    },
    changeActiveItem(index) {
      this.activeItemIndex = index
      clearInterval(this.interval)
      this.interval = this.activateCarousel()
    }
  }
}
</script>


<style lang="scss" scoped>
.carousel {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 100rem;

  &__controls {
    display: flex;
  }

  &__control {
    height: 1.5rem;
    width: 1.5rem;
    border-radius: 50%;
    border: 1px solid $color-primary;
    transition: all 1s;
    cursor: pointer;

    &:not(:last-child) {
      margin-right: 1rem;
    }

    &--active {
      background-color: $color-primary;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 3rem;
  }

  &__icon {
    position: absolute;
    font-size: 12rem;
    color: $color-primary;
    line-height: 1;
    top: 0;
    left: 50%;
    transform: translate(-50%, -10%);
  }

  &__quote {
    margin-top: 8rem;
    font-size: 2rem;
    color: $color-font-dark;
    text-align: center;
  }

  &__author {
    color: $color-font-light;
    font-family: $font-display;
  }
}

.slide-enter-active,
.slide-leave-active {
  transition: all 1s ease-out;
}

.slide-enter {
  opacity: 0.1;
  transform: translateX(20rem);
}
.slide-leave-to {
  opacity: 0;
  transform: translateX(-20rem);
}
</style>
