<template>
  <button class="g-button">
    <g-icon :name="icon" v-if="icon && iconPosition === 'left'"></g-icon>
    <slot></slot>
    <g-icon :name="icon" v-if="icon && iconPosition === 'right'"></g-icon>
  </button>
</template>

<script>
export default {
  props: {
    icon: {},
    iconPosition: {
      default: "left",
      validator(value) {
        return value !== "left" || value !== "right";
      },
    },
  },
};
</script>

<style scoped lang="scss">
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
