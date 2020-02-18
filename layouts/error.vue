<template>
  <div>
    This is error page
    <h1>{{ error.statusCode }} not Found</h1>
  </div>
</template>

<script>
export default {
  layout: 'error-layout',
  props: {
    error: {
      type: Object,
      default: null
    }
  }
  }
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>
