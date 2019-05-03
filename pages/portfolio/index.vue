<template>
  <div class="container">
    <image-gallery
      :controls="controls"
      :items="items"
    />
  </div>
</template>

<script>
import ImageGallery from '~/components/Shared/ImageGallery/ImageGallery'
import img4 from '~/assets/images/4.jpg'
import img6 from '~/assets/images/6.jpg'
import img8 from '~/assets/images/8.jpg'
import img9 from '~/assets/images/9.jpg'
import img18 from '~/assets/images/18.jpg'
import img19 from '~/assets/images/19.jpg'
import img21 from '~/assets/images/21.jpg'
import img22 from '~/assets/images/22.jpg'
import img23 from '~/assets/images/23.jpg'
import img25 from '~/assets/images/25.jpg'
import img26 from '~/assets/images/26.jpg'
import img29 from '~/assets/images/29.jpg'

export default {
  components: {
    ImageGallery
  },
  data() {
    return {
      activeCategory: 'All',
      activeItemIndex: 0,
      modalOpen: false,
      controls: [
        { display: 'All', selector: '*' },
        { display: 'Haircuts', selector: '.haircuts' },
        { display: 'Coloring', selector: '.coloring' },
        { display: 'Barber', selector: '.barber' },
        { display: 'Shaving', selector: '.shaving' },
        { display: 'Hairstyle', selector: '.hairstyle' },
        { display: 'Massages', selector: '.massages' }
      ],
      items: [
        { img: img18, classes: ['grid__item', 'grid__item--x3', 'haircuts'] },
        { img: img19, classes: ['grid__item', 'grid__item--x3', 'haircuts'] },
        { img: img6, classes: ['grid__item', 'grid__item--x3', 'coloring'] },
        { img: img4, classes: ['grid__item', 'grid__item--x3', 'massages'] },
        { img: img8, classes: ['grid__item', 'grid__item--x3', 'shaving'] },
        { img: img9, classes: ['grid__item', 'grid__item--x3', 'hairstyle'] },
        { img: img21, classes: ['grid__item', 'grid__item--x3', 'coloring'] },
        { img: img22, classes: ['grid__item', 'grid__item--x3', 'barber'] },
        { img: img23, classes: ['grid__item', 'grid__item--x3', 'barber'] },
        { img: img25, classes: ['grid__item', 'grid__item--x3', 'shaving'] },
        { img: img26, classes: ['grid__item', 'grid__item--x3', 'hairstyle'] },
        { img: img29, classes: ['grid__item', 'grid__item--x3', 'massages'] }
      ]
    }
  }
}
</script>
