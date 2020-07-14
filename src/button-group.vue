<template>
  <div class="g-button-group"><slot></slot></div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.g-button-group {
  display: inline;
  .g-button {
    border-radius: 0 !important;
    margin-left: -1px;
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
