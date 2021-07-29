<template>
    <setting-certi-info
        :datalist = "datalist"
        @onDelete = "onDelete"
    />

</template>

<script>
import SettingCertiInfo from '@/components/SettingCertiInfo.vue'


export default  { 
  data() {
    return {
      datalist: {
        ip : "000.000.000.1",
        equip : "EquipName",
        host : "HostName",
        model : "ModelName",
        connect : "SSH",
        list  : [
          {id : "Port" ,value : "22"},
          {id : "ID" ,value : "root"},
          {id : "Password" ,value : "123"}]
      }
    }
  },
  components:{
    SettingCertiInfo
  },
  methods: {
    onDelete(){
      console.log("click delete");
    }
  }
}
</script>
