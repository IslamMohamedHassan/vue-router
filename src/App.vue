<template>
  <TheNavigation/>
  <div class = "container">
    <RouterView/>
  </div>

</template>

<script>
import TheNavigation from './components/TheNavigation.vue';
import { RouterView } from 'vue-router';
  export default {
   
    data () {
      return {
        
      }
    },
    components : {
      TheNavigation
    }
  }
</script>