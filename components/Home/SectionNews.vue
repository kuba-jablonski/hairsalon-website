<template>
  <section class="news">
    <div class="container">
      <div class="news__heading">
        <h2>Latest News</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, facere?</p>
      </div>
      <div class="news__cards">
        <news-card
          v-for="card in cards"
          :key="card.img"
          :img="card.img"
          :comments="card.comments"
          :date="card.date"
        >
          <template slot="heading">
            Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.
          </template>
          <template>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</template>
        </news-card>
      </div>
    </div>
  </section>
</template>

<script>
import img1 from '~/assets/images/1.jpg'
import img2 from '~/assets/images/2.jpg'
import img3 from '~/assets/images/3.jpg'
import NewsCard from '~/components/Shared/NewsCard/NewsCard'

export default {
  components: {
    NewsCard
  },
  data() {
    return {
      cards: [
        {
          img: img1,
          date: 'September 27',
          comments: 10,
          heading: "Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.",
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.'
        },
        {
          img: img2,
          date: 'September 27',
          comments: 10,
          heading:
            'Finally: How to Make Your Agressively Straight Hair Hold a Curl',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.'
        },
        {
          img: img3,
          date: 'September 27',
          comments: 10,
          heading:
            'Yes, Emilia Clarke Just Cut Off All Her Hair Into a Tiny Bob',
          text:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.'
        }
      ]
    }
  }
}
</script>


<style lang="scss" scoped>
.news {
  &__heading {
    text-align: center;
    margin-bottom: 4rem;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 3rem;

    @include respond(md) {
      grid-template-columns: 1fr 1fr;
    }

    @include respond(sm) {
      grid-template-columns: 1fr;
    }
  }
}
</style>
