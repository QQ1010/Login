<template>
 <v-form>
   <v-container>
     <v-row>
       <v-col
       cols="12"
       sm="6"
       md="3"
       >
       <v-text-field
       v-model="username"
       label="Username"
       :rules="[() => !!username || 'This field is required.']"
       :error-messages="errorMessages"
       clearable
       >
       </v-text-field>
       </v-col>
     </v-row>
     <v-row>
       <v-col
        cols="12"
        sm="6"
        md="3"
       >
        <v-text-field
        v-model="password"
        label="Password"
        :rules="[() => !!password || 'This field is required.']"
        :error-messages="errorMessages"
        clearable
        >
        </v-text-field>
      </v-col>
     </v-row>
   <v-card-actions>
   <v-row>
     <v-col
     cols="12"
     sm="6"
     >
     <v-btn
     depressed
     @click="check"
     >
     Submit
     </v-btn>
     </v-col>
   </v-row>
   </v-card-actions>
   </v-container>
 </v-form>
</template>

<script>
export default {
  name: 'Signin',
  data () {
    return {
      username: '',
      password: '',
      errorMessages: ''
    }
  },
  methods: {
    check () {
      if (this.username === 'admin' && this.password === 'csieweek') alert('Lodin success!')
      else alert('Wrong Answer')
    }
  }
}
</script>
