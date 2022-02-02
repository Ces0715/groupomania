<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
   <p>{{abonnes}} x personnes inscrites </p> 
   <button v-on:click="subscribe()">s'inscrire </button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function(){
    return {
      abonnes :0,
    }
  },
  methods: {
    subscribe:function(){
      this.abonnes++;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: red;
}

p{
  font-size: 18px;
}
</style>
