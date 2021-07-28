<template>
  <div class = "Setting">
    <label>인증 정보</label>
    <div class = "CertiInfo">
        <essential-info-setting></essential-info-setting>
        <connect-info-setting></connect-info-setting>
        <button>삭제</button>
    </div>
  </div>
</template>

<script>
import ConnectInfoSetting from '@/components/ConnectInfoSetting.vue'
import EssentialInfoSetting from '@/components/EssentialInfoSetting.vue'

export default  { 
  components:{
    ConnectInfoSetting,
    EssentialInfoSetting
  }
}
</script>
<style scoped>
    button{
        width : 80px;
        height : 26px;
        margin : 0px 40px 0px 10px;
        border-style : solid;
        border-color :rgb(173, 182, 190);
        background-color :rgb(225, 235, 255);
        float : right;
    }

    .CertiInfo{
        padding : 15px 0px 0px 10px;
        margin : 20px 20px 0px 20px;
        border:1px solid grey;
        width : 570px;
        height : 600px;

    }
    .Setting label{
        margin-left : 15px;
    }
    .Setting {
        margin-top : 10px;
    }
</style>