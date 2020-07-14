<template>
  <div class="g-button-group"><slot></slot></div>
</template>

<script>
export default {
  mounted() {
    for (let name of this.$el.children) {
      if (name.nodeName !== "BUTTON") {
        console.warn(`您需要传入的是button标签，但你传入了${name.nodeName}`);
      }
    }
  },
};
</script>

<style scoped lang="scss">
.g-button-group {
  display: inline;
  .g-button {
    border-radius: 0 !important;
    &:not(:first-child) {
      margin-left: -1px;
    }
    &:first-child {
      border-top-left-radius: var(--border-radius) !important;
      border-bottom-left-radius: var(--border-radius) !important;
    }
    &:last-child {
      border-top-right-radius: var(--border-radius) !important;
      border-bottom-right-radius: var(--border-radius) !important;
    }
    &:hover {
      position: relative;
      z-index: 1;
    }
  }
}
</style>
