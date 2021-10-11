<template>
<a 
    class="external-link"
    v-if="isExtirnal"
    target="_blank" 
    rel="noopener"
    :href="to"
><slot /></a>
  <router-link class="internal-link" v-else v-bind="$props"><slot /></router-link>
</template>

<script>
import { RouterLink } from "vue-router"

export default {
    props: {
        ...RouterLink.props
    },
    computed: {
        isExtirnal(){
            return typeof this.to === 'string' && this.to.startsWith('http')
        }
    }
}
</script>

<style>

</style>