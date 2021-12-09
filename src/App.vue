<script lang="ts">
import { defineComponent } from 'vue';
import Vueuser from './components/Vueuser.vue'

export default defineComponent({
  name: 'App',
  components:{
    Vueuser
  }
})
</script>

<template>
  <div class="container-main">
    
    <Vueuser />
  </div>
</template>