<template>
  <div class="card">
    <img :src="img">
    <div class="card__info">
      <div class="card__date">
        <icon-clock class="icon" /> {{ date }}
      </div>
      <span>|</span>
      <div class="card__comments">
        <icon-chat class="icon" /> {{ comments }}
      </div>
    </div>
    <div class="card__cardtext">
      <h4>
        <slot name="heading" />
      </h4>
      <p>
        <slot />
      </p>
    </div>
  </div>
</template>

<script>
import IconClock from '~/assets/images/clock.svg?inline'
import IconChat from '~/assets/images/bubbles4.svg?inline'

export default {
  components: {
    IconClock,
    IconChat
  },
  props: {
    img: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    comments: {
      type: Number,
      required: true
    }
  }
}
</script>


<style lang="scss" scoped>
.card {
  cursor: pointer;

  img {
    width: 100%;
    margin-bottom: 1rem;
  }

  h4 {
    transition: all 0.3s;
  }

  &:hover {
    h4 {
      color: $color-primary;
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
