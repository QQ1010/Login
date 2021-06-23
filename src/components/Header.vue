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
          @click="options = SIGNIN"
          >
          Signin</v-btn>

        <v-btn
          color=#FFA07A
          v-on="on"
          v-bind="click"
          @click="options = SIGNUP"
          >
          Signup</v-btn>
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

            <v-card-text v-if="options === SIGNIN">
              <Signin></Signin>
            </v-card-text>
            <v-card-text v-if="options === SIGNUP">
              <Signup></Signup>
            </v-card-text>
          </v-card>
        </v-dialog>
    </div>
</template>

<script>
import Signin from '@/components/Signin.vue'
import Signup from '@/components/Signup.vue'

const SIGNIN = 0
const SIGNUP = 1

export default {
  data () {
    return {
      dialog: false,
      SIGNIN,
      SIGNUP,
      options: '',
    }
  },
  components: {
    Signin,Signup
  },
}
</script>
