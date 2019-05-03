<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
      <image-gallery
        :controls="controls"
        :items="items"
        square
      />
      <div class="work__cta">
        <base-button @click="modalOpen = true">
          View all work
        </base-button>
      </div>
    </section>
  </div>
</template>

<script>
import ImageGallery from '~/components/Shared/ImageGallery/ImageGallery'
import img6 from '~/assets/images/6.jpg'
import img5 from '~/assets/images/5.jpg'
import img7 from '~/assets/images/7.jpg'
import img8 from '~/assets/images/8.jpg'
import img9 from '~/assets/images/9.jpg'

export default {
  components: {
    ImageGallery
  },
  data() {
    return {
      controls: [
        { display: 'All', selector: '*' },
        { display: 'Haircuts', selector: '.haircuts' },
        { display: 'Dye', selector: '.dye' },
        { display: 'Shave', selector: '.shave' },
        { display: 'Hairstyle', selector: '.hairstyle' }
      ],
      items: [
        { img: img5, classes: ['grid__item', 'grid__item--x4', 'haircuts'] },
        {
          img: img6,
          classes: ['grid__item', 'grid__item--x4', 'grid__item--lgl', 'dye']
        },
        {
          img: img7,
          classes: ['grid__item', 'grid__item--x4', 'grid__item--lgs', 'shave']
        },
        { img: img8, classes: ['grid__item', 'grid__item--x4', 'hairstyle'] },
        { img: img9, classes: ['grid__item', 'grid__item--x4', 'dye'] }
      ]
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
