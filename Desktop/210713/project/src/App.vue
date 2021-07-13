<template>
    <div id = "acompo">
        <InputComponent @OnClick="OnClick"></InputComponent>
        <ListComponent v-bind:key="items.keys" v-bind:value="items.values" @OnRemove="OnRemove"></ListComponent>
    </div>
</template>

<script>
import InputComponent from '@/components/InputComponent.vue'
import ListComponent from '@/components/ListComponent.vue'

export default  {
  data(){
     return{
       items : [ 
          { keys:'', values: '' }
        ]
      }
   },
    
   created() {
        if (this.items.length > 0){
            for(var i = 0; i < this.items.length; i++) {
                this.items.keys.push(this.items(i).key);
                this.items.values.push(this.items(i).value);
            }
        }
    },
 
   methods: {
      OnClick(key,value){
          // localStorage.setItem(items.key,items.key);
          // localStorage.setItem(items.value,items.value);
          // this.items.keys.push(key);
          // this.items.values.push(value);
          this.items.push({
            keys : key,
            values : value
          });
      },
        OnRemove(items,index) {
          // localStorage.removeItem(items.key);
          // localStorage.removeItem(items.value);
          this.items.splice(index,1);
          //index에서 1개의 요소 제거
        }
  },
  
  components : {
      InputComponent,
      ListComponent
   },
}
</script>

<style scoped>

</style>
