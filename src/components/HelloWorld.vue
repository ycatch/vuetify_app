<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Hello world
        </h1>

        <p class="subheading font-weight-regular">
          For help and collaboration with other Vuetify developers,
        </p>
        <p class="name">Message: {{ nickname }}</p>
        <input class="input" v-model="nickname" placeholder="Message">
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'nickname',

    data () {
        return {
            nickname: ''
        }
    }
  }
</script>
