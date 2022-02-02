<template>
    <div class="card">
        <h1 class="card_title" v-if="mode == 'login'"> Se connecter</h1>
        <h1 class="card_title" v-else> Inscription</h1>
        <p class="card_subtitle"  v-if="mode == 'login'"> Tu n'as pas encore de compte? <span class="card_action" @click="switchToCreateAccount()"> Créer un compte </span></p>
        <p class="card_subtitle"  v-else> Tu as déja compte? <span class="card_action" @click="switchToLogin()"> Se connecter </span></p>
    
    <div class="form-row" v-if="mode == 'create'">
        <input v-model="Nom" class="form-row_input" type="text" placeholder="Nom"/>
    </div>
    <div class="form-row" v-if="mode == 'create'">
        <input v-model="prenom" class="form-row_input" type="text" placeholder="Prenom"/>
    </div>
    <div class="form-row">
        <input v-model="email" class="form-row_input" type="text" placeholder="Email"/>
    </div>
    <div class="form-row">
        <input v-model="login" class="form-row_input" type="text" placeholder="Login"/>
    </div>
    <div class="form-row">
        <input v-model="password" class="form-row_input" type="password" placeholder="Mot de passe"/>
    </div>
<div class="form-row">
    <button class = "button button --disabled" v-if="mode == 'login'">
        Se connecter
    </button>
    <button class = "button" :class= "{'button --disabled': !validateFields()}" v-else>
        Créer un compte
    </button>
</div>

    </div>
</template>


<script>
export default {
  name: 'Login',
  data: function(){
      return {
          mode:'login',
      }
  },
  computed:{
validateFields: function(){
    if(this.mode == 'create') {
        if (this.email != "" && this.prenom != "" && this.nom != "" && this.password !="" ){
            return true;
        } else {
            return false;
        }
    }
    
}
  },
  methods:{
      switchToCreateAccount:function(){
          this.mode ='create';
      },
     switchToLogin:function(){
         this.mode = "login";
     }
  }
}

</script>

<style scoped>


input{
    width: 300px;
   height: 30px;
}

.form-row {
padding-bottom: 10px;
}
</style>
