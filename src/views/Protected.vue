<template>
  <div>
      <h1>Greetings {{username}}</h1>
      <button @click="logout" class="btn">Logout</button> &nbsp;
      <router-link :to="{name: 'invoices'}">
        <button class="btn">Invoices</button>
      </router-link>
  </div>
</template>

<script>
export default {
  data(){
    return{
      username: window.user
    }
  },
  methods: {
    logout(){
      window.user = null
      this.$router.push({name: 'Home'})
    }
  }
}
</script>

<style>

</style>