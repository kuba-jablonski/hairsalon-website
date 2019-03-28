<template>
  <div>
    <home-hero />
    <main>
      <section-about />
      <section-services />
      <section-whyus />
      <section-work />
      <section-personnel />
      <section-news />
    </main>
  </div>
</template>

<script>
import HomeHero from '~/components/Home/HomeHero'
import SectionAbout from '~/components/Home/SectionAbout'
import SectionServices from '~/components/Home/SectionServices'
import SectionWhyus from '~/components/Home/SectionWhyus'
import SectionWork from '~/components/Home/SectionWork'
import SectionPersonnel from '~/components/Home/SectionPersonnel'
import SectionNews from '~/components/Home/SectionNews'

export default {
  components: {
    HomeHero,
    SectionAbout,
    SectionServices,
    SectionWhyus,
    SectionWork,
    SectionPersonnel,
    SectionNews
  }
}
</script>
