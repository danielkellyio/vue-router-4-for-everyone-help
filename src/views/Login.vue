<template>
  <div class="login">
      <form class="form" @submit.prevent="login">
          <h1>Login</h1>

          <label for="username">Username</label>
          <input v-model="username" type="text" class="input" name="username">

          <label for="password">Password</label>
          <input v-model="password" type="text" class="input" name="password">
          
          <button class="btn" >Login</button>
      </form>
  </div>
</template>

<script>
import {ref} from 'vue'
import { useRoute, useRouter } from 'vue-router'

export default {
    setup(){
        const username = ref('')
        const password = ref('')
        const route = useRoute()
        const router = useRouter()

        const login = () => {
            window.user = username.value
            const redirectPaath = route.query.redirect || '/protected'
            router.push(redirectPaath)
        }

        return {
            username,
            password,
            login
        }
    },
}
</script>

<style>

</style>