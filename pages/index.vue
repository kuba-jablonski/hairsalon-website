<template>
  <div>
    <home-hero />
    <main>
      <section-about />
      <section-services />
      <section-whyus />
      <section-work />
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
