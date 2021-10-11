<template>
  <div id="nav">
    <AppLink id="logo" to="/">Home</AppLink>
    <AppLink to="/about">About</AppLink>  
    <AppLink 
            v-for="destination in destinations"
            :key="destination.id"
            :to="{name: 'destination.show', params: {id: destination.id, slug: destination.slug}}"
          >
            {{destination.name}}
    </AppLink>
    <AppLink :to="{name: 'protected'}">Protected</AppLink>
    <AppLink to="https://www.google.ru/?gws_rd=ssl">Vue School</AppLink>
  </div>
</template>

<script>
import saurceData from '@/data.json'
import AppLink from './AppLink.vue'

export default {
    data(){
        return{
            destinations: saurceData.destinations
        }
    }
}
</script>

<style>
    #nav .vue-school-active-link{
        color: greenyellow;
    }
</style>