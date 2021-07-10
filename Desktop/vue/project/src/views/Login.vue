<template>
  <div class ="login">
    <div id="topmenu">
      <TopMenuComponent></TopMenuComponent>
    </div>
  </div>
</template>
<script>
import TopMenuComponent from '@/components/TopMenuComponent.vue'

export default {
    name: 'Login',
    components :{
        TopMenuComponent
    }
}
</script>
<style scoped>
  #topmenu {
    border-style : none none solid none;
    border-width : 1px;
    border-color : rgb(192, 192, 192);
    padding-bottom: 20px;
    
  }
</style>

