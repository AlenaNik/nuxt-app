<template>
 <div>
   <h1> About page </h1>
   <p>{{ title }}</p>
   <n-link to="/"> Home </n-link>
 </div>
</template>

<script>

  export default {
    asyncData(){
      return { title: 'About from async '}
    },
    head () {
      return {
        title: `About page`,
        meta: [
          { hid: 'description', name: 'description', content: 'About page description is here' }
        ]
      }
    }
  }
</script>
