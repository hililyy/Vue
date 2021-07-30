<template>
  <div class = "setting">
    <div class = "certiInfo">
        <setting-essential-info
            :datalist = "datalist"
        />
        <setting-connect-info
            :datalist = "datalist"
        />
        <button @click = "onDelete">삭제</button>
    </div>
  </div>
</template>

<script>
import SettingConnectInfo from '@/components/SettingConnectInfo.vue'
import SettingEssentialInfo from '@/components/SettingEssentialInfo.vue'

export default  { 
    props : {
      datalist : Object,
    },

  components:{
    SettingConnectInfo,
    SettingEssentialInfo
  },

  methods : {
    onDelete(){
          this.$emit('onDelete');
        }
  }
}
</script>
<style scoped>
    .setting {
        margin-top : 10px;
    }

    .setting label{
        margin-left : 15px;
    }

    .certiInfo{
        padding : 15px 0px 0px 10px;
        margin : 20px 20px 0px 20px;
        border:1px solid grey;
        min-width : 550px;
        height : 650px;
    }

    button{
        width : 80px;
        height : 30px;
        margin : 0px 40px 0px 0px;
        border-style : solid;
        border-color :rgb(173, 182, 190);
        background-color :rgb(225, 235, 255);
        float : right;
    }
</style>