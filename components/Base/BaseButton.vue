<template>
  <button
    class="btn"
    v-on="$listeners"
  >
    <slot />
  </button>
</template>

<style lang="scss" scoped>
.btn {
  position: relative;
  font-family: $font-display;
  font-size: 1.5rem;
  border: 1px solid black;
  border-radius: 50px;
  outline: none;
  background-color: transparent;
  text-transform: uppercase;
  cursor: pointer;
  display: flex;
  min-width: 14rem;
  height: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.5s ease-in-out;

  &:hover {
    box-shadow: -3px 2px 40px 8px rgba(15, 15, 15, 0.15);
    border-color: $color-primary;
    background-color: $color-primary;
    color: #fff;
  }
}
</style>
