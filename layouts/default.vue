<template>
  <div>
    <layout-header />
    <nuxt />
    <layout-footer />
  </div>
</template>

<script>
import LayoutHeader from '~/components/Layout/LayoutHeader'
import LayoutFooter from '~/components/Layout/LayoutFooter'

export default {
  components: {
    LayoutHeader,
    LayoutFooter
  }
}
</script>
