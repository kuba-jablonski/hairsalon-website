<template>
  <div class="container">
    <page-header>Blog</page-header>
    <div
      ref="grid"
      class="grid"
    >
      <div class="card" />
    </div>
  </div>
</template>

<script>
import imagesLoaded from 'imagesloaded'
import PageHeader from '~/components/Shared/PageHeader/PageHeader'

export default {
  components: {
    PageHeader
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
  }
}
</script>
