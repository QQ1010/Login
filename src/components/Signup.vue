<template>
<div align="center">
 <v-form>
    <img src="@/assets/NOJ.png" title="NOJ logo">
   <v-container fluid class="d-flex flex-column align-center login">
     <div class="text-h5">創立一個新帳號</div>
     <v-row>
       <v-col
       cols="12"
       sm="10"
       md="12"
       >
       <v-text-field
       v-model="username"
       prepend-icon="mdi-account"
       label="使用者名稱"
       :rules="loginRules.username"
       :error-messages="errorMessages"
       clearable
       >
       </v-text-field>
       <v-text-field
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
        <v-text-field 
        v-model="checkPassword"
        prepend-icon="mdi-lock"
        label="再次輸入密碼"
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
      創立
      </v-btn>
   </v-card-actions>
   </v-container>
 </v-form>
</div>
</template>

<script>

export default {
  name: 'Signup',
  
  data: () => ({
      email: '',
      username: '',
      password: '',
      errorMessages: '',
      checkPassword: '',
      isShowPassword: false,
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
