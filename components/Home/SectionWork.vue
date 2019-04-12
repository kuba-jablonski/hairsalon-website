<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
      <div class="image-grid">
        <!-- <img
          class="grid-item"
          src="~/assets/images/5.jpg"
        >
        <div class="aspect">
          <div class="aspect__inner">
            <img
              class="grid-item grid-item-2"
              src="~/assets/images/1.jpg"
            >
          </div>
        </div>
        <div class="aspect">
          <div class="aspect__inner">
            <img
              class="grid-item"
              src="~/assets/images/7.jpg"
            >
          </div>
        </div>
        <img
          class="grid-item"
          src="~/assets/images/8.jpg"
        >
        <img
          class="grid-item"
          src="~/assets/images/9.jpg"
        > -->

        <div class="grid-item">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/5.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item grid-item-2">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/1.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item grid-item-3">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/7.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/8.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/9.jpg">
            </div>
          </div>
        </div>
      </div>
      <div class="work__cta">
        <base-button>View all work</base-button>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  mounted() {
    if (process.browser) {
      // const Masonry = require('masonry-layout')
      // // eslint-disable-next-line no-console
      // console.log(Masonry)

      // const msnry = new Masonry('.image-grid', {
      //   // options
      //   itemSelector: '.grid-item',
      //   percentPosition: true,
      //   columnWidth: '.grid-sizer'
      //   // gutter: 10
      // })
      // // eslint-disable-next-line no-console
      // console.log(msnry)
      const Shuffle = require('shufflejs').default

      // Shuffle.options = {
      //   gutterWidth: 10
      // }

      const element = document.querySelector('.image-grid')
      // eslint-disable-next-line no-console
      console.log(Shuffle)
      const shuffleInstance = new Shuffle(element, {
        itemSelector: '.grid-item'
      })
      // eslint-disable-next-line no-console
      console.log(shuffleInstance)
    }
  }
}
</script>


<style lang="scss" scoped>
.grid-item {
  width: 25%;
  padding: 1rem;

  @include respond(md) {
    width: 50%;
  }
}

.grid-item-2 {
  width: 50%;
}

.grid-item-3 {
  @include respond(md) {
    width: 100%;
  }
}

img {
  width: 100%;
  height: 100%;
}

.aspect {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  overflow: hidden;
}

.aspect__inner {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

/* Add more aspect ratios here */
.aspect--16x9 {
  padding-bottom: 56.25%;
}

// .image-grid {
//   display: grid;
//   grid-template-columns: repeat(4, 1fr);
//   grid-template-rows: repeat(2, 24rem);
//   grid-gap: 4rem;
//   margin-bottom: 8rem;
// }

// .grid-item {
//   width: 100%;
//   height: 100%;
// }

// .grid-item-1 {
//   grid-column: span 1;
//   grid-row: span 1;
// }

// .grid-item-2 {
//   grid-column: span 2;
//   grid-row: span 2;
// }

// .work {
//   background: white;

//   &__heading {
//     text-align: center;
//   }

//   &__cta {
//     display: flex;
//     justify-content: center;
//   }
// }
</style>
