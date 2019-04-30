<template>
  <div>
    <layout-nav />
    <nuxt />
    <layout-footer />
  </div>
</template>

<script>
import LayoutNav from '~/components/Layout/LayoutNav/LayoutNav'
import LayoutFooter from '~/components/Layout/LayoutFooter'

export default {
  components: {
    LayoutNav,
    LayoutFooter
  }
}
</script>
