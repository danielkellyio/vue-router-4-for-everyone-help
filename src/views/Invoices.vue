<template>
  <div>
      <h1>Invoices</h1>
       <button @click="logout" class="btn">Logout</button>
  </div>
</template>

<script>
import { onBeforeRouteLeave } from "vue-router"

export default {
    setup(){
        onBeforeRouteLeave((to, from) => {
            const answer = window.confirm(
                'You want to leave, are not you?'
            )
            if(!answer) return false
        }) 
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