<template>
  <div>
    <section class="personnel">
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
    </section>
    <div class="container">
      <div class="section-break" />
    </div>
  </div>
</template>

<script>
import FacebookIcon from '~/assets/images/facebook.svg?inline'
import TwitterIcon from '~/assets/images/twitter.svg?inline'
import LinkedinIcon from '~/assets/images/linkedin.svg?inline'
import DribbbleIcon from '~/assets/images/dribbble.svg?inline'

export default {
  components: {
    FacebookIcon,
    TwitterIcon,
    LinkedinIcon,
    DribbbleIcon
  }
}
</script>


<style lang="scss" scoped>
.section-break {
  border-bottom: 1px solid #e6e6e6;
}

.thumbnail {
  background-image: url('~assets/images/14.png');
  background-repeat: no-repeat;
  position: absolute;
  width: 55.5rem;
  height: 70%;
  top: 0;
  right: 50%;
  z-index: -1;

  @include respond(md) {
    opacity: 0.2;
  }

  @include respond(sm) {
    display: none;
  }
}

.personnel {
  position: relative;
  z-index: 1;

  &::before {
    position: absolute;
    width: 100%;
    height: 70%;
    content: '';
    top: 0;
    right: 0;
    background-color: #f6f9f9;
    z-index: -1;
  }

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
</style>
