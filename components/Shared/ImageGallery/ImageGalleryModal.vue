<template>
  <base-modal
    center
    :show="show"
    @close="close"
  >
    <button
      class="btn btn--left"
      @click.stop="back"
    >
      <icon-left class="icon" />
    </button>
    <img
      class="img"
      :src="items[activeItemIndex].img"
      @click.stop
    >
    <button
      class="btn btn--right"
      @click.stop="forward"
    >
      <icon-right class="icon" />
    </button>
  </base-modal>
</template>

<script>
import IconLeft from '~/assets/images/chevron-left.svg?inline'
import IconRight from '~/assets/images/chevron-right.svg?inline'

export default {
  components: {
    IconLeft,
    IconRight
  },
  props: {
    show: Boolean,
    activeItemIndex: {
      type: Number,
      required: true
    },
    items: {
      type: Array,
      required: true
    }
  },

  methods: {
    close() {
      this.$emit('close')
    },
    back() {
      this.$emit('changeIndex', this.activeItemIndex - 1)
    },
    forward() {
      this.$emit('changeIndex', this.activeItemIndex + 1)
    }
  }
}
</script>


<style lang="scss" scoped>
.btn {
  background-color: $color-primary;
  opacity: 0.8;
  border: none;
  outline: none;
  width: 9rem;
  height: 10rem;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: opacity 0.3s;

  &--left {
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
  }

  &--right {
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
  }

  .icon {
    width: 5rem;
    height: 5rem;
    fill: white;
  }

  &:hover {
    opacity: 1;
  }

  @include respond(sm) {
    width: 6rem;
    height: 7rem;

    .icon {
      width: 3rem;
      height: 3rem;
    }
  }
}

.img {
  max-width: 99%;
  max-height: 99%;
  width: 60rem;
}
</style>
