<template>
<div align="center">
 <v-form>
    <img src="@/assets/NOJ.png" title="NOJ logo">
   <v-container fluid class="d-flex flex-column align-center login">
     <div class="text-h5">登入</div>
     <v-radio-group v-model="loginMethod" row class="mt-8" hide-details>
       <v-radio label="透過使用者名稱登入"/>
       <v-radio label="透過電子信箱登入" />
     </v-radio-group>
     <v-row >
       <v-col
       cols="12"
       sm="10"
       md="12"
       >
       <v-text-field v-if="loginMethod === USERNAME"
       v-model="username"
       label="使用者名稱"
       prepend-icon="mdi-account"
       :rules="loginRules.username"
       :error-messages="errorMessages"
       clearable
       >
       </v-text-field>
       <v-text-field v-else
       v-model="email"
       prepend-icon="mdi-email"
       label="電子信箱"
       :rules="loginRules.email"
       :error-messages="errorMessages"
       clearable
       >
       </v-text-field>
      <v-text-field 
        v-model="password"
        prepend-icon="mdi-lock"
        label="密碼"
        :rules="loginRules.password"
        :error-messages="errorMessages"
        clearable
        :type="isShowPassword ? 'text' : 'password'" 
        :append-icon="isShowPassword ? 'mdi-eye' : 'mdi-eye-off'"
        @click:append="isShowPassword = !isShowPassword"
        >
        </v-text-field>
        </v-col>
     </v-row>
      <v-card-actions>
      <v-btn
      color=#FFA07A
      block
      class="mt-4"
      @click="Submit"
      >
      登入
      </v-btn>
   </v-card-actions>
   </v-container>
 </v-form>
</div>
</template>

<script>
const USERNAME = 0
const EMAIL = 1

export default {
  name: 'Signin',
  
  data: () => ({
      isLogin: false,
      email: '',
      username: '',
      password: '',
      errorMessages: '',
      isShowPassword: false,
      loginMethod: USERNAME,
      USERNAME,
      EMAIL,
      loginRules: {
        username: [val => !!val || '請輸入使用者名稱'],
        email: [val => !!val || '請輸入您的電子郵件'],
        password: [val => !!val || '請輸入您的密碼'],
      },
  }),
  methods: {
    Submit() {
      
    }   //還不會寫 
  }
}
</script>
