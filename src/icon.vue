<template>
  <svg class="icon">
    <use :xlink:href="`#i-${name}`"></use></svg
></template>

<script>
export default {
  props: ["name"],
};
</script>

<style scoped lang="scss">
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
}
</style>
