<template>
  <h2 class="e-title">
    {{ label }}
  </h2>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: null,
    },
  },
};
</script>

<style lang="scss" scoped>
.e-title {
  font-size: 22px;
  font-weight: 600;
  line-height: 1.4;
  color: #1A1F27;
  text-align: left;
}
</style>