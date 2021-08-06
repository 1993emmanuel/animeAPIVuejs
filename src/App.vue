<template>
<div class="app">
  <NavBarComponent />
  <router-view/>
</div>
</template>

<script>

import NavBarComponent from './components/NavBarComponent';

export default{
  components:{
    NavBarComponent
  },
  setup(){
    return { NavBarComponent }
  }
};
</script>

<style lang="scss">
*{
  padding: 0;
  margin : 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', sans-serif;
}
a{
  text-decoration: none;
}
header{
  padding-top: 50px;
  padding-bottom: 50px;
  h1{
      color:#888;
      font-size: 42px;
      font-weight: 400;
      text-align: center;
      text-transform: uppercase;
      margin-bottom: 30px;
      strong{
        color : #313131;
      }
      &:hover{
        color: #313131;
      }
  }
  .search-box{
    display: flex;
    justify-content: center;
    padding-left: 30px;
    padding-right: 30px;
    .search-field{
      appearance: none;
      background: none;
      border:none;
      outline: none;
      background-color: #f3f3f3;
      box-shadow: 0 4px 8px rgba(0,0,0,0.15);
      display: block;
      width: 100%;
      max-width: 600px;
      padding: 15px;
      border-radius: 8px;
      color : #313131;
      font-size: 20px;
      transition: 0.4s;
      &:focus, &:valid{
        color: #AAA;
        background-color: #313131;
        box-shadow: 0px 0px 0px rgba(0,0,0,0.15);
      }
    }
  }
}
main{
  max-width: 1200px;
  margin: 0 auto;
  padding-left: 30px;
  padding-right: 30px;
  .cards{
    display :flex;
    flex-wrap: wrap;
    margin: 0 -8px;
  }
}
</style>
