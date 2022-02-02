<template>
  <div class="home"> 
    <groupomania1/> 
    <HelloWorld/>  
  </div>
</template>

<script>
// @ is an alias to /src
import groupomania1 from '@/components/groupomania1.vue'
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
     HelloWorld,groupomania1
  }
}
</script>
