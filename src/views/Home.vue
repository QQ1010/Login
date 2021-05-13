<template>
  <div class="home">
    <v-img
      max-height="600"
      max-width="2000"
      src="../assets/login.png"
    ></v-img>
    <Signin></Signin>
  </div>
</template>

<script>
// @ is an alias to /src
import Signin from '@/components/Signin.vue'

export default {
  name: 'home',
  components: {
    Signin
  }
}
</script>
