<template>
  <header class="header">
    <h1>
      <slot />
    </h1>
    <p class="header__pagination">
      <nuxt-link
        to="/"
        class="header__home"
      >
        <icon-home class="icon" />Home
      </nuxt-link>
      <icon-double-right class="icon" />
      <span>
        <slot name="link" />
      </span>
    </p>
  </header>
</template>

<script>
import IconHome from '~/assets/images/home-outline.svg?inline'
import IconDoubleRight from '~/assets/images/angle-double-right.svg?inline'

export default {
  components: {
    IconHome,
    IconDoubleRight
  }
}
</script>

<style lang="scss" scoped>
.icon {
  width: 1.6rem;
  height: 1.6rem;
  fill: #252525;
  transition: all 0.3s;
}

.header {
  padding: 8rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;

  &__pagination {
    display: flex;
    align-items: center;

    :not(:last-child) {
      margin-right: 1rem;
    }
  }

  &__home {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #252525;
    transition: all 0.3s;

    .icon {
      margin-right: 2px;
    }

    &:hover {
      color: $color-primary;

      .icon {
        fill: $color-primary;
      }
    }
  }
}
</style>
