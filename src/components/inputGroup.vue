<template>
  <div class="input-group">
    <div class="input-group-prepend">
      <p class="input-group-text">{{ title }}</p>
    </div>
    <slot/>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Title'
    }
  }
}
</script>
<style scoped>
.input-group-prepend {
  color: #737791;
  font-size: 14px;
  line-height: 0;
}
</style>