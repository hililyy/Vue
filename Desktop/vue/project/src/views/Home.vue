<template>
  <div class="home">
    <div id="login">
        <LoginComponent></LoginComponent>
    </div>
    <div id="join">
      <JoinComponent></JoinComponent>
    </div>
  </div>
</template>

<script>
import LoginComponent from '@/components/LoginComponent.vue'
import JoinComponent from '@/components/JoinComponent.vue'

export default {
  name: 'Home',
  components: {
    LoginComponent,
    JoinComponent  
  }
}
</script>

<style>
  #login {
    border : 1px solid rgb(199, 199, 199);
    margin : 100px 0px 10px 10px;
    padding : 30px 10px 50px 10px;
  } 

  #join {
    border : 1px solid rgb(199, 199, 199);
    margin : 0px 0px 10px 10px;
    padding : 10px 10px 10px 10px;
  }
</style>
