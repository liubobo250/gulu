<template>
  <button class="g-button" @click="$emit('click')">
    <span v-if="icon && iconPosition === 'left'"
      ><g-icon v-if="loading" name="loading" class="loading"></g-icon>
      <g-icon :name="icon" v-else></g-icon
    ></span>

    <slot></slot>
    <span v-if="icon && iconPosition === 'right'"
      ><g-icon v-if="loading" name="loading" class="loading"></g-icon>
      <g-icon :name="icon" v-else></g-icon
    ></span>
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
    loading: {
      default: false,
    },
  },
};
</script>

<style scoped lang="scss">
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
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
  .loading {
    animation: spin 2s infinite linear;
  }
}
</style>
