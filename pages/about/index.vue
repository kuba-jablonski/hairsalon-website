<template>
  <div>
    <page-header>
      About Us
      <template v-slot:link>
        About
      </template>
    </page-header>
    <div class="container">
      <div class="about">
        <div class="about__title">
          <div class="about__title-bg">
            History
          </div>
          <p>New York &middot; Since 2004</p>
          <h2>About Our Stories</h2>
        </div>
        <p class="about__text">
          At Hairone Salon, we are lorem ipsum dolor sit amet, consectetur adipi elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
      </div>
    </div>
    <div class="video">
      <div class="container">
        <div class="video__card">
          <img
            class="video__img"
            src="~/assets/images/44.jpg"
          >
          <button class="video__btn">
            Play
          </button>
        </div>
        <div class="data">
          <div class="display">
            <div class="display__bg">
              Case
            </div>
            <div class="display__number">
              457
            </div>
            <div class="display__name">
              projects completed
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Client
            </div>
            <div class="display__number">
              343
            </div>
            <div class="display__name">
              happy customers
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Award
            </div>
            <div class="display__number">
              379
            </div>
            <div class="display__name">
              award winners
            </div>
          </div>
          <div class="display">
            <div class="display__bg">
              Style
            </div>
            <div class="display__number">
              97
            </div>
            <div class="display__name">
              different hairstyles
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="carousel-section">
        <testimonial-carousel />
      </div>
    </div>
    <div class="personnel">
      <div class="thumbnail" />
      <div class="container">
        <div class="personnel__top">
          <div class="personnel__text">
            <h2>Our Experts</h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis nostrud exercitation ullamco laboris nisi ut aliquip ex.
            </p>
            <div class="personnel__cert">
              <img src="~/assets/images/certificate-1.webp">
              <img src="~/assets/images/certificate-2.webp">
              <img src="~/assets/images/certificate-3.webp">
            </div>
          </div>
        </div>
        <div class="personnel__cards">
          <div class="personnel__card">
            <div class="personnel__image-box">
              <div class="personnel__overlay">
                <div class="personnel__icon-bg">
                  <facebook-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <twitter-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <linkedin-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <dribbble-icon class="personnel__icon" />
                </div>
              </div>
              <img src="~/assets/images/10.jpg">
            </div>
            <div class="personnel__card-text">
              <h4>Mila Hartley</h4>
              <p>Hairdresser</p>
            </div>
          </div>
          <div class="personnel__card">
            <div class="personnel__image-box">
              <div class="personnel__overlay">
                <div class="personnel__icon-bg">
                  <facebook-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <twitter-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <linkedin-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <dribbble-icon class="personnel__icon" />
                </div>
              </div>
              <img src="~/assets/images/11.jpg">
            </div>
            <div class="personnel__card-text">
              <h4>Teigan Duran</h4>
              <p>Stylist</p>
            </div>
          </div>
          <div class="personnel__card">
            <div class="personnel__image-box">
              <div class="personnel__overlay">
                <div class="personnel__icon-bg">
                  <facebook-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <twitter-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <linkedin-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <dribbble-icon class="personnel__icon" />
                </div>
              </div>
              <img src="~/assets/images/12.jpg">
            </div>
            <div class="personnel__card-text">
              <h4>Tanya Ramsey</h4>
              <p>Hairstylist</p>
            </div>
          </div>
          <div class="personnel__card">
            <div class="personnel__image-box">
              <div class="personnel__overlay">
                <div class="personnel__icon-bg">
                  <facebook-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <twitter-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <linkedin-icon class="personnel__icon" />
                </div>
                <div class="personnel__icon-bg">
                  <dribbble-icon class="personnel__icon" />
                </div>
              </div>
              <img src="~/assets/images/13.jpg">
            </div>
            <div class="personnel__card-text">
              <h4>Donna Carr</h4>
              <p>Barber</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PageHeader from '~/components/Shared/PageHeader/PageHeader'
import TestimonialCarousel from '~/components/About/TestimonialCarousel'
import FacebookIcon from '~/assets/images/facebook.svg?inline'
import TwitterIcon from '~/assets/images/twitter.svg?inline'
import LinkedinIcon from '~/assets/images/linkedin.svg?inline'
import DribbbleIcon from '~/assets/images/dribbble.svg?inline'

export default {
  components: {
    PageHeader,
    TestimonialCarousel,
    FacebookIcon,
    TwitterIcon,
    LinkedinIcon,
    DribbbleIcon
  }
}
</script>

<style lang="scss" scoped>
.personnel {
  position: relative;
  z-index: 1;
  padding: 8rem 0;
  background-color: #f6f9f9;

  &__top {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 2rem;
  }

  &__text {
    grid-column: 2;
    z-index: 1;

    @include respond(md) {
      grid-column: 1/3;
    }

    p {
      margin-bottom: 4rem;
    }
  }

  &__cert {
    margin-bottom: 4rem;

    & > * {
      margin-right: 2rem;
    }
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 3rem;

    img {
      width: 100%;
      filter: grayscale(1);
      transition: filter 0.3s;
      -webkit-transition: 0.3s -webkit-filter;
      -moz-transition: 0.3s -moz-filter;
      -moz-transition: 0.3s filter;
      -ms-transition: 0.3s -ms-filter;
      -o-transition: 0.3s -o-filter;
    }
  }

  &__card {
    border: 1px solid #e5e5e5;
    background-color: white;

    @include respond(md) {
      grid-column: span 2;
    }

    @include respond(xs) {
      grid-column: span 4;
    }

    &:hover {
      img {
        filter: none;
      }

      .personnel__card-text h4 {
        color: $color-primary;
      }

      .personnel__overlay {
        opacity: 1;
      }
    }
  }

  &__card-text {
    padding: 2rem;
  }

  &__image-box {
    position: relative;
  }

  &__overlay {
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(white, 0.7);
    display: flex;
    justify-content: space-around;
    align-items: center;
    transition: all 0.3s;
    opacity: 0;
    z-index: 1;
  }

  &__icon-bg {
    background-color: transparent;
    height: 4.5rem;
    width: 4.5rem;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.3s;
    cursor: pointer;

    &:hover {
      background-color: $color-primary;

      .personnel__icon {
        fill: white;
      }
    }
  }

  &__icon {
    height: 1.5rem;
    width: 1.5rem;
    transition: fill 0.3s;
  }
}

.thumbnail {
  background-image: url('~assets/images/14.png');
  background-repeat: no-repeat;
  position: absolute;
  width: 55.5rem;
  height: 100%;
  top: 0;
  right: 50%;
  z-index: -1;

  @include respond(md) {
    display: none;
  }
}

.carousel-section {
  padding: 8rem 0;
  display: flex;
  justify-content: center;
}

.display {
  position: relative;

  &__bg {
    font-family: $font-display;
    font-size: 5rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    display: flex;
    justify-content: center;
  }

  &__number {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 5.1rem;
  }

  &__name {
    position: absolute;
    bottom: -2rem;
    left: 50%;
    width: 100%;
    transform: translateX(-50%);
    text-align: center;
    text-transform: uppercase;
    font-size: 1.2rem;
    color: $color-font-light;
  }
}

.data {
  position: relative;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 3rem;
  padding-bottom: 8rem;
  z-index: 1;
}

.video {
  position: relative;

  &::before {
    position: absolute;
    bottom: 0;
    right: 0;
    content: '';
    height: 60%;
    background-color: #f6f9f9;
    width: 100%;
  }

  &__card {
    position: relative;
    box-shadow: 2px 4px 10px rgba(black, 0.1);
    padding: 2rem;
    margin-bottom: 8rem;
    background-color: white;
  }

  &__img {
    width: 100%;
    display: block;
  }

  &__btn {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 8rem;
    height: 8rem;
    border-radius: 50%;
    background-color: $color-primary;
    border: none;
    outline: none;
    cursor: pointer;
  }
}

.about {
  display: grid;
  grid-template-columns: 3fr 4fr;
  grid-gap: 8rem;
  align-items: start;
  padding-bottom: 8rem;

  &__title {
    position: relative;

    p {
      position: absolute;
      top: 10%;
      right: 0;
      margin: 0;
    }

    h2 {
      position: absolute;
      bottom: 0;
      right: 0;
      margin: 0;
    }
  }

  &__title-bg {
    font-family: $font-display;
    font-size: 10rem;
    text-transform: uppercase;
    font-weight: bold;
    line-height: 1;
    color: rgba($color-primary, 0.1);
    display: flex;
    justify-content: flex-end;
  }

  &__text {
    color: $color-font-dark;
    font-style: italic;
    font-size: 2rem;
  }
}
</style>
