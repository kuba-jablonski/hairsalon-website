<template>
  <transition name="slide">
    <div
      v-if="show"
      class="nav-mobile"
    >
      <button
        class="nav-mobile__close-btn"
        @click="$emit('close')"
      >
        <icon-close class="nav-mobile__icon" />
      </button>
      <ul class="nav-mobile__items">
        <nuxt-link
          v-for="item in items"
          :key="item.link"
          tag="li"
          :to="item.link"
          class="nav-mobile__item"
        >
          {{ item.display }}
        </nuxt-link>
      </ul>
      <base-button class="nav-mobile__cta">
        Book Now
      </base-button>
    </div>
  </transition>
</template>

<script>
import IconClose from '~/assets/images/close.svg?inline'

export default {
  components: {
    IconClose
  },
  props: {
    show: Boolean,
    items: {
      type: Array,
      required: true
    }
  },
  watch: {
    '$route.name'() {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss" scoped>
.nav-mobile {
  position: fixed;
  top: 0;
  left: 0;
  width: 30rem;
  max-width: 100%;
  height: 100vh;
  background-color: white;
  z-index: 10;
  display: flex;
  flex-direction: column;
  box-shadow: 1px 0 5px rgba(0, 0, 0, 0.12);

  &__cta {
    margin-top: 2rem;
    align-self: center;
  }

  &__close-btn {
    padding: 1.5rem 2rem;
    align-self: flex-end;
    border: none;
    outline: none;
    background: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }

  &__icon {
    display: block;
    position: relative;
    right: 0;
    fill: #858585;
  }

  &__items {
    display: flex;
    flex-direction: column;
  }

  &__item {
    font-size: 1.4rem;
    background-color: #f2f4f8;
    border-bottom: 1px solid rgba(255, 255, 255, 0.5);
    padding: 1rem;
    transition: all 0.3s;
    cursor: pointer;

    &:hover {
      color: $color-primary;
    }
  }
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.5s;
}
.slide-enter,
.slide-leave-to {
  transform: translateX(-100%);
}
</style>
