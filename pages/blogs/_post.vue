<template>
  <div>
    <h1>{{ slug.post }}</h1>
  </div>
</template>


<script>
  export default {
    data(){
      return {
        slug: this.$route.params
      }
    },
    created() {
      // console.log(this.$route.params)
    }
  }
</script>
