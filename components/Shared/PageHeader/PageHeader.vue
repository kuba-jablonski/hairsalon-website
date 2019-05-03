<template>
  <header class="header">
    <h1>Portfolio</h1>
    <p class="p">
      <nuxt-link
        to="/"
        class="home"
      >
        <icon-home class="icon" />Home
      </nuxt-link>
      <icon-double-right class="icon" /> <span>Portfolio</span>
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
.p {
  display: flex;
  align-items: center;

  :not(:last-child) {
    margin-right: 1rem;
  }
}

.home {
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
}
</style>
