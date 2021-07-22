<template>
      <div id = "test">
        <h1>{{"파일 설정"}}</h1>
          <ul>
            <li style="margin-right:90px;">key</li>
            <li style="margin-right:120px;">value</li>
            <li style="margin-right:30px;">동작</li>
          </ul>
          <div class="content" :style="cssVariable">
            <ListComponent 
                :data = "data" 
                @OnRemove = "OnRemove"/>
            <InputComponent 
                :data = "data"
                @change= "change"
                :form = "form" />
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
        form : Array
  //   add_disable : Array,
  //   remove_disable : Function,
  //   change : Function,
  //    title : String,
   },
 
   methods: {
      change(key,value){
          this.data.push({
              keys : key,
              values : value
          });

          if(!this.form[0].option.includes(key)){
              this.form[0].option.push(key);
          }
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
    border: 1px solid grey;
    border-top-width : 0px;
  }
  ul { 
    padding : 10px 0px 10px 10px;
    margin-bottom : 0; 
    border:1px solid grey;
  }
  h1{
    text-align: left;
    font-size: medium;
    margin : 15px 0px 10px 10px;

  }
</style>
