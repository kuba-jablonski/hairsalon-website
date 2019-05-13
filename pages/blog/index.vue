<template>
  <div class="container">
    <div class="blog">
      <page-header>
        Our Blog
        <template v-slot:link>
          Blog
        </template>
      </page-header>
      <div
        ref="grid"
        class="grid"
      >
        <news-card
          v-for="card in cards"
          :key="card.img"
          class="grid__item"
          :img="card.img"
          :comments="card.comments"
          :date="card.date"
        >
          <template slot="heading">
            {{ card.heading }}
          </template>
          <template>{{ card.text }}</template>
        </news-card>
      </div>

      <base-button
        class="blog__btn"
        primary
      >
        Load More
      </base-button>
    </div>
  </div>
</template>

<script>
import imagesLoaded from 'imagesloaded'
import PageHeader from '~/components/Shared/PageHeader/PageHeader'
import NewsCard from '~/components/Shared/NewsCard/NewsCard'
import img6 from '~/assets/images/6.jpg'
import img2 from '~/assets/images/2.jpg'
import img3 from '~/assets/images/3.jpg'
import img4 from '~/assets/images/4.jpg'
import img23 from '~/assets/images/23.jpg'
import img9 from '~/assets/images/9.jpg'
import img21 from '~/assets/images/21.jpg'
import img22 from '~/assets/images/22.jpg'
import img29 from '~/assets/images/29.jpg'

export default {
  components: {
    PageHeader,
    NewsCard
  },
  data() {
    return {
      cards: [
        {
          img: img6,
          date: 'September 27',
          comments: 10,
          heading: "Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.",
          text:
            'Most people recognize the CFDA Awards for its slew of perfect gowns and skin-tight.'
        },
        {
          img: img2,
          date: 'September 27',
          comments: 10,
          heading:
            'Finally: How to Make Your Agressively Straight Hair Hold a Curl',
          text:
            'So I sought out an actual professional, i.e. celeb hairstylist Justine Marjan.'
        },
        {
          img: img3,
          date: 'September 27',
          comments: 10,
          heading:
            'Yes, Emilia Clarke Just Cut Off All Her Hair Into a Tiny Bob',
          text:
            'Last night, Clarke appeared on Late Night with Seth Meyers, wearing a charcoal blazer.'
        },
        {
          img: img4,
          date: 'September 27',
          comments: 10,
          heading:
            'How the media encourages – and sustains – political warfare',
          text:
            'The quiet consumption of news can sustain a polarized political environment.'
        },
        {
          img: img23,
          date: 'September 27',
          comments: 10,
          heading: 'Lorem ipsum dolor sit amet.',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptatum, voluptates.'
        },

        {
          img: img9,
          date: 'September 27',
          comments: 10,
          heading: 'Lorem ipsum dolor sit amet.',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptatum, voluptates.'
        },
        {
          img: img21,
          date: 'September 27',
          comments: 10,
          heading: 'Lorem ipsum dolor sit amet.',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptatum, voluptates.'
        },
        {
          img: img22,
          date: 'September 27',
          comments: 10,
          heading: 'Lorem ipsum dolor sit amet.',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptatum, voluptates.'
        },
        {
          img: img29,
          date: 'September 27',
          comments: 10,
          heading: 'Lorem ipsum dolor sit amet.',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptatum, voluptates.'
        }
      ]
    }
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

<style lang="scss" scoped>
.blog {
  border-bottom: 1px solid #e5e5e5;

  &__btn {
    margin: 0 auto 8rem auto;
  }
}

.grid {
  margin: 0 -2rem 4rem -2rem;

  &__item {
    padding: 2rem;
    width: 33%;

    &:hover .overlay {
      opacity: 1;
    }

    &:hover img {
      transform: scale(1.2);
    }

    @include respond(md) {
      width: 50%;
    }

    @include respond(xs) {
      width: 100%;
    }

    &--lgl {
      width: 50%;

      @include respond(xs) {
        width: 100%;
      }
    }

    &--lgs {
      @include respond(md) {
        width: 100%;
      }
    }
  }
}
</style>
