<template>
  <section class="news">
    <div class="container">
      <div class="news__heading">
        <h2>Latest News</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, facere?</p>
      </div>
      <div class="news__cards">
        <div class="news__card">
          <img src="~/assets/images/1.jpg">
          <div class="news__info">
            <div class="news__date">
              <icon-clock class="icon" /> September 27
            </div>
            <span>|</span>
            <div class="news__comments">
              <icon-chat class="icon" /> 10
            </div>
          </div>
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
        <div class="news__card">
          <img src="~/assets/images/2.jpg">
          <div class="news__info">
            <div class="news__date">
              <icon-clock class="icon" /> September 27
            </div>
            <span>|</span>
            <div class="news__comments">
              <icon-chat class="icon" /> 10
            </div>
          </div>
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
        <div class="news__card">
          <img src="~/assets/images/3.jpg">
          <div class="news__info">
            <div class="news__date">
              <icon-clock class="icon" /> September 27
            </div>
            <span>|</span>
            <div class="news__comments">
              <icon-chat class="icon" /> 10
            </div>
          </div>
          <div class="news__cardtext">
            <h4>Nina Dobrev Got a Major and Doesn't Look like Nina Dobrev.</h4>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit veritatis rem enim fugiat voluptas magni quaerat inventore ut illum molestias.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import IconClock from '~/assets/images/clock.svg?inline'
import IconChat from '~/assets/images/bubbles4.svg?inline'

export default {
  components: {
    IconClock,
    IconChat
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
  }

  &__card {
    img {
      width: 100%;
      margin-bottom: 1rem;
    }
  }

  &__info {
    font-size: 1.4rem;
    color: #acacac;
    display: flex;
    align-items: center;
    margin-bottom: 1rem;

    & > * {
      display: flex;
      align-items: center;
    }

    & > *:not(:last-child) {
      margin-right: 2rem;
    }
  }
}

.icon {
  width: 1.4rem;
  height: 1.4rem;
  fill: #acacac;
  margin-right: 4px;
}
</style>
