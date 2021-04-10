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
          For help and collaboration with other Vuetify developers
        </p>

        <div class="form-group">
            <label for="form_title">Input: </label>
            <ValidationProvider rules="max:5" v-slot="{ errors }">
                <input 
                    v-model="greeting"
                    type="text"
                    placeholder="Your Message is here !!"
                >
                <span> {{ errors[0] }}</span>
            </ValidationProvider>
            <p class="name">Output: {{ greeting }}</p>
        </div>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  import { ValidationProvider } from "vee-validate";
  import { extend } from 'vee-validate';
  import { max } from 'vee-validate/dist/rules';

  extend('max', {
    ...max,
    message: 'Exceeds maximum length'
  });

  export default {
    components: {
        ValidationProvider
    },

    name: 'greeting',
    data () {
        return {
            greeting: ''
        }
    }
  }
</script>
