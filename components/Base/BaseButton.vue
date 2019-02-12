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
  font-family: inherit;
  font-size: 1.6rem;
  border: 1px solid black;
  border-radius: 50px;
  outline: none;
  background-color: transparent;
  text-transform: uppercase;
  cursor: pointer;
  display: flex;
  min-width: 15rem;
  height: 4.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
