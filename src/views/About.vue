<template>
  <div class="container mt-4">
    <div class="row">
      <div class="col-12">
        <h1 class="text-center lead text-uppercase">Recursos del Proyecto</h1>
      </div>
    </div>
    <div class="row mt-4">
      <div class="col-xs-12 col-sm-6 col-md-6 col-lg-4 text-center mb-2">
        <h3 class="text-center lead m-3">Tecnologias Usadas</h3>
        <img src="@/assets/logo.png" alt="vue" class="img-fluid">
        <p class="text-center vue"><strong>Vue</strong></p>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-6 col-lg-4 mb-2">
        <h3 class="text-center lead m-3">API Consumida</h3>
          <h4 class="text-center">API: <a :href="apiUsada.link" target="_blank">{{apiUsada.name}}</a> </h4>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-6 col-lg-4 mb-2 bg-dark text-white">
        <h3 class="text-center lead m-3">Desarrollados By:</h3>
        <p>Name: <strong>{{developerInfo.name}}</strong></p>
        <p>Career: <strong>{{developerInfo.carrear}}</strong></p>
        <p>Git-Hub: <strong><a :href="developerInfo.github" target="_blank">My Account</a></strong></p>
        <p>Created : <strong>{{calYear}}</strong></p>
      </div>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue';
export default{
  name : 'About',
  computed:{
    calYear(){
      const fechaActual = new Date();
      return fechaActual.getFullYear();
    }
  },
  setup(){
    const apiUsada = ref({});
    const developerInfo = ref({});
    developerInfo.value = {
      name : 'Emmanuel Hernandez Mejia',
      carrear : 'Engineer of Computer',
      github : 'https://github.com/1993emmanuel',
    }
    apiUsada.value = {
      link : 'https://jikan.docs.apiary.io/#',
      name : `Jikan 
      API UNOFFICIAL MYANIMELIST API`,
    }
    return { apiUsada, developerInfo }
  }
};
</script>

<style lang="scss" scoped>
strong{
  a{
    text-decoration: none;
    color:#fff;
  }
}
h4{
  a{
    text-decoration: none;
    color:#000;
  }
}
.vue{
  a{
    text-decoration: none;
    color:#000;
  }
}
</style>


