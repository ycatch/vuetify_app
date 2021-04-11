<template>
  <v-container>
    <v-row class="text-left">
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

        <form>
            <ValidationProvider v-slot="{ errors }" rules="max:3">
                <v-text-field
                    v-model="greeting"
                    :error-messages="errors"
                    label="Input"
                    :success="valid"
                ></v-text-field>
            </ValidationProvider>
            <p>Output: {{ greeting }}</p>
        </form>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  import { ValidationProvider, extend, localize } from "vee-validate";
  import { max } from 'vee-validate/dist/rules';
  import ja from 'vee-validate/dist/locale/ja';

  extend('max', max);
  localize('ja', ja)

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
