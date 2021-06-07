<template>
    <div class="text-center">
    <v-dialog
        v-model="dialog"
        width="500"
    >
        <template v-slot:activator="{ on,click }">
        <v-app-bar
          color="#636060"
          dark
          dense
        >
        <v-btn
          color=#FFA07A
          v-on="on"
          v-bind="click"
          >
          Signin</v-btn>
        </v-app-bar></template>

        <v-card 
          max-height="1000"
          max-width="1000"
          shaped
          center
          outlined
         >
            <v-card-title>
              <v-toolbar
            color=#636060
            dark>
            <v-btn
            icon
            dark
            @click="dialog=false"
            >
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </v-toolbar>
            </v-card-title>

            <v-card-text>
                <Signin></Signin>
            </v-card-text>
          </v-card>
        </v-dialog>
    </div>
</template>

<script>

import Signin from '@/components/Signin.vue'

export default {
  data () {
    return {
      dialog: false,
    }
  },
  components: {
    Signin
  }
}
</script>
