<template>
  <button class="g-button">
    <svg class="icon" v-if="icon && iconPosition === 'left'">
      <use :xlink:href="`#i-${icon}`"></use></svg
    ><slot></slot
    ><svg class="icon" v-if="icon && iconPosition === 'right'">
      <use :xlink:href="`#i-${icon}`"></use>
    </svg>
  </button>
</template>

<script>
export default {
  props: {
    icon: {},
    iconPosition: {
      default: "left",
      validator(value) {
        if (value !== "left" && value !== "right") {
          return false;
        } else {
          return true;
        }
      },
    },
  },
};
</script>

<style scoped lang="scss">
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
}
.g-button {
  font-size: var(--font-size);
  height: var(--button-height);
  padding: 0 1em;
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background-color: var(--button-bg);
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background-color: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
}
</style>
