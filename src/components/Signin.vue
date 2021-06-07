<template>
<div align="center">
 <v-form>
    <img src="@/assets/NOJ.png" title="NOJ logo">
   <v-container fluid class="d-flex flex-column align-center login">
     <div>Sign in</div>
     <v-radio-group v-model="loginMethod" row class="mt-8" hide-details>
       <v-radio label="透過username登入"/>
       <v-radio label="透過email登入" />
     </v-radio-group>
     <v-row>
       <v-col
       cols="12"
       sm="10"
       md="12"
       >
       <v-text-field
       v-model="username"
       label="使用者名稱"
       :rules="loginRules.username"
       :error-messages="errorMessages"
       clearable
       >
       </v-text-field>
       </v-col>
     </v-row>
     <v-row>
       <v-col
        cols="12"
        sm="10"
        md="12"
       >
        <v-text-field
        v-model="password"
        label="密碼"
        :rules="loginRules.password"
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
</div>
</template>

const USERNAME = 0
const EMAIL = 1

<script>
export default {
  name: 'Signin',
  data: () => ({
      email: '',
      username: '',
      password: '',
      errorMessages: '',
      loginMethod: 'USERNAME',
      USERNAME: '',
      EMAIL: '',
      loginRules: {
        username: [val => !!val || '請輸入使用者名稱'],
        email: [val => !!val || '請輸入您的電子郵件'],
        password: [val => !!val || '請輸入您的密碼'],
      },
  }),
  methods: {
    check () {
      if (this.username === 'admin' && this.password === 'csieweek') alert('Lodin success!')
      else alert('Wrong Answer')
    }
  }
}
</script>
