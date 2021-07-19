<template>
      <div id = "test">
          <ul style ="padding-left:20px; padding-bottom:10px; margin-bottom:0; border-bottom:1px solid grey;">
            <li style="margin-right:90px;">key</li>
            <li style="margin-right:130px;">value</li>
            <li style="margin-right:30px;">동작</li>
          </ul>
          <div class="content" :style="cssVariable">
            <ListComponent 
                :data = "data" 
                @OnRemove = "OnRemove"/>
            <InputComponent 
                @change= "change"/>
          </div>
      </div>
</template>

<script>
import InputComponent from '@/components/InputComponent.vue'
import ListComponent from '@/components/ListComponent.vue'

export default  {
   props : {
    max_height : Number,
    data : Array,
  //   add_disable : Array,
  //   remove_disable : Function,
  //   change : Function,
  //   // title : String,
   },
  
  data(){
     return{
      }
   },
    
   created() {
        if (this.data.length > 0){
            for(var i = 0; i < this.data.length; i++) {
                this.data.keys.push(this.data[i].key);
                this.data.values.push(this.data[i].value);
            }
        }
    },
 
   methods: {
      change(key,value){
          this.data.push({
            keys : key,
            values : value
          });
      },
        OnRemove(data,index) {
          this.data.splice(index,1);
        }
  },
  computed:{
    cssVariable(){
      return{
        '--max_height' : this.max_height + 'px',
      }
    },
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
    height: var(--max_height); 
    overflow-y:scroll;
    border:1px solid grey;
  }
</style>
