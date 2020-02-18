<template>
  <v-app>
    <v-content>
    <v-toolbar>
    <v-toolbar-title>
      <v-btn text>
      <nuxt-link to="/"> Home ⛈️ </nuxt-link>
      </v-btn>
    </v-toolbar-title>
    <v-toolbar-items>
    <v-btn text>
     <nuxt-link to="/weather-app">
       Weather App </nuxt-link>
    </v-btn>
    </v-toolbar-items>
  </v-toolbar>
      <transition>
        <nuxt/>
      </transition>
    </v-content>
  </v-app>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  a {
    text-decoration: none;
    color: white;
  }
</style>
