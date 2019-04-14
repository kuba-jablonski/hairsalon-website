<template>
  <div class="container">
    <section class="work">
      <div class="work__heading">
        <h2>Our Work</h2>
        <p>Quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
      <div class="grid-controls">
        <button @click="filter('*')">
          All
        </button>
        <button @click="filter('.haircuts')">
          Haircuts
        </button>
        <button @click="filter('.dye')">
          Dye
        </button>
        <button @click="filter('.shave')">
          Shave
        </button>
        <button @click="filter('.hairstyle')">
          Hairstyle
        </button>
      </div>
      <div class="image-grid">
        <div class="grid-item haircuts">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/5.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item dye grid-item-2">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/1.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item shave grid-item-3">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/7.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item hairstyle">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/8.jpg">
            </div>
          </div>
        </div>
        <div class="grid-item dye">
          <div class="aspect">
            <div class="aspect__inner">
              <img src="~/assets/images/9.jpg">
            </div>
          </div>
        </div>
      </div>
      <div class="work__cta">
        <base-button>
          View all work
        </base-button>
      </div>
    </section>
  </div>
</template>

<script>
let iso

export default {
  mounted() {
    if (process.browser) {
      const Isotope = require('isotope-layout')
      const elem = document.querySelector('.image-grid')
      iso = new Isotope(elem, {
        itemSelector: '.grid-item'
      })
      // eslint-disable-next-line no-console
    }
  },
  methods: {
    filter(itemClass) {
      iso.arrange({
        filter: itemClass
      })
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

  @include respond(xs) {
    width: 100%;
  }
}

.grid-item-2 {
  width: 50%;

  @include respond(xs) {
    width: 100%;
  }
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
