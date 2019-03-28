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
      <section-booking />
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
import SectionBooking from '~/components/Home/SectionBooking'

export default {
  components: {
    HomeHero,
    SectionAbout,
    SectionServices,
    SectionWhyus,
    SectionWork,
    SectionPersonnel,
    SectionNews,
    SectionBooking
  }
}
</script>
