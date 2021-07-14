<template>
      <div id = "test">
          <ul style ="padding-left:20px; padding-bottom:10px; margin-bottom:0; border-bottom:1px solid grey;">
            <li style="margin-right:90px;">key</li>
            <li style="margin-right:130px;">value</li>
            <li style="margin-right:30px;">동작</li>
          </ul>
          <div class="content">
          <ListComponent v-bind:items ="items" @OnRemove="OnRemove"/>
          <InputComponent @OnClick="OnClick"/>
          </div>
      </div>
</template>

<script>
import InputComponent from '@/components/InputComponent.vue'
import ListComponent from '@/components/ListComponent.vue'

export default  {
  data(){
     return{
        items : [],
      }
   },
    
   created() {
        if (this.items.length > 0){
            for(var i = 0; i < this.items.length; i++) {
                this.items.keys.push(this.items[i].key);
                this.items.values.push(this.items[i].value);
            }
        }
    },
 
   methods: {
      OnClick(key,value){
          this.items.push({
            keys : key,
            values : value
          });
      },
        OnRemove(items,index) {
          this.items.splice(index,1);
        }
  },
  
  components : {
      InputComponent,
      ListComponent
   },
}
</script>

<style scoped>
  #test {
    text-align: center;
    width : 370px;
    height: 200px;
  }
  li {
    padding-left:0px;
    display : inline;
    list-style:none;
  }
  .content {
    height:200px;
    overflow-y:scroll;
    border:1px solid grey;
  }
</style>
