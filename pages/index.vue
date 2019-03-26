<template>
  <div>
    <home-hero />
    <main>
      <div class="container">
        <section-about />
        <section-services />
      </div>
      <section-whyus />
      <div class="container">
        <section-work />
      </div>
    </main>
  </div>
</template>

<script>
import HomeHero from '~/components/Home/HomeHero'
import SectionAbout from '~/components/Home/SectionAbout'
import SectionServices from '~/components/Home/SectionServices'
import SectionWhyus from '~/components/Home/SectionWhyus'
import SectionWork from '~/components/Home/SectionWork'

export default {
  components: {
    HomeHero,
    SectionAbout,
    SectionServices,
    SectionWhyus,
    SectionWork
  }
}
</script>
