<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
      <gallery />
      <div class="work__cta">
        <base-button @click="modalOpen = true">
          View all work
        </base-button>
      </div>
    </section>
    <me-modal
      :show="modalOpen"
      @close="modalOpen = false"
    />
  </div>
</template>

<script>
import MeModal from '~/components/MeModal'
import Gallery from '~/components/Shared/Gallery/Gallery'

export default {
  components: {
    MeModal,
    Gallery
  },
  data() {
    return {
      modalOpen: false
    }
  }
}
</script>


<style lang="scss" scoped>
.work {
  &__heading {
    text-align: center;
    margin-bottom: 4rem;
  }

  &__cta {
    display: flex;
    justify-content: center;
  }
}
</style>
