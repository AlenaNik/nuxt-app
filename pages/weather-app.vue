<template>
  <v-content>
    <v-container>
        <v-flex xs12>
          <v-card class="d-inline-block mx-auto">
            <v-container>
              <v-row justify="space-between">
                <v-col cols="auto">
                  <v-card-text>Here is the card</v-card-text>
                  <v-img
                    height="200"
                    width="200"
                    src="https://images.unsplash.com/photo-1560346983-ffa0a154e978?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1884&q=80"
                  ></v-img>
                </v-col>

                <v-col
                  cols="auto"
                  class="text-center pl-0"
                >
                  <v-row
                    class="flex-column ma-0 fill-height"
                    justify="center"
                  >
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
          <v-card class="d-inline-block mx-10">
            <v-container>
              <v-row justify="space-between">
                <v-col cols="auto">
                  <v-card-text>
                    <v-layout justify-center v-if="weather.weather">
                      <v-flex >
                        <h4>Temperature</h4>
                        <p class="display-1"> {{ weather.name }}</p>
                        <p class="display-1"> {{ weather.main.temp }}</p>
                        <span class="display-1">{{ weather.weather[0].description }}</span>
                        <img :src="icon" alt="weather-icon">
                      </v-flex>
                    </v-layout>

                  </v-card-text>
                </v-col>

                <v-col
                  cols="auto"
                  class="text-center pl-0"
                >
                  <v-row
                    class="flex-column ma-0 fill-height"
                    justify="center"
                  >
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-flex>

          <v-col cols="12" sm="6" md="3">
            <v-form @submit.prevent="getWeatherInfo">
              <v-text-field
                v-model="city"
                label="Enter City Name"
              ></v-text-field>
            </v-form>
          </v-col>
    </v-container>
  </v-content>

</template>

<script>
  export default {
    data() {
      return {
        city: 'Madrid',
        weather: {}
      }
    },
    created() {
      this.getWeatherInfo()
    },
    computed: {
      icon() {
        return this.weather.weather ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png`
          : ''
      }
    },
    methods: {
      getWeatherInfo() {
        this.$axios.$get(`http://api.openweathermap.org/data/2.5/weather?q=${this.city}&APPID=c6eba2ee0a23cd0b9459a2e6e24cf23f`)
          .then(res => (this.weather = res))
      }
    }
  }
</script>
