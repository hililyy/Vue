<template>
      <div class = "setting">
        <div class = "title">
            <label>접속 정보</label>
        </div>
            <label class ="menu1">접속방식</label>
            <span class ="menu2">
              <label>key</label>
              <label>value</label>
            </span>
        
              <div class = "mode"> 
                <div v-for = "(item,index) in ModeList" v-bind:key = "index" class="modelist">

                  <span v-if = "item == datalist.connect">
                    <input type = "radio" name="radio" checked disabled>
                    <label>{{item}}</label>
                  </span>

                  <span v-else>
                    <input type = "radio" name="radio" disabled>
                    <label>{{item}}</label>
                  </span>
                </div>
              </div>
        
              <div class = "textBox">
                <div v-for="(item,index) in datalist.list" v-bind:key="index">
                
                    <select disabled>
                        <option selected>{{item.id}}</option>
                    </select>
                  
                    <span v-if = "item.id == 'Password'">
                        <input type = "password" v-model ="item.value" disabled>
                    </span>

                    <span v-else>
                        <input type = "text" v-model ="item.value" disabled>
                    </span>
                  
                </div>
              </div>
        </div>

</template>

<script>
export default  {
  created(){
    if(this.datalist.ip == undefined){
      this.datalist.connect = "";
      for(var i=0;i<this.datalist.list.length;i++){
        this.datalist.list[i].id = "";
        this.datalist.list[i].value = "";
      }
    }
  },
    props : {
      datalist : Object
    },
    data() {
      return {
        ModeList : ["SSH","API","HMAC","GUI"],
      }
    },
}
  
</script>

<style scoped>

  .setting { 
    border:1px solid grey;
    margin : 20px 20px 40px 20px;
    grid-template-rows: 40px 40px 200px;
    grid-template-columns: 200px 1fr ;
    display : grid;
  }

  .title {
    padding : 10px 0px 10px 10px;
    border: solid grey; 
    border-width : 0px 0px 1px 0px;
    grid-column : 1 / 3;
    grid-row : 1 / 2;
  }

  .menu { 
    border: solid grey; 
    border-width : 0px 0px 1px 0px;
    padding-top :20px;
  }

  .menu1{
    grid-row : 2 / 3;
    grid-column : 1 / 2;
    padding : 20px 0px 0px 40px;

  }

  .menu2{
    grid-row : 2 / 3;
    grid-column : 2 / 3;
    padding-top : 20px;
  }
  .menu2 label {
    margin-right : 100px;
  }

  .mode {
    margin : 10px 90px 0px 40px;
    grid-row : 3 / 4;
    grid-column : 1 / 2;
  }

  .modelist {
    margin : 20px 0px 10px 0px;
    list-style: none;
  }

  .mode label{
    margin-right : 3px;
    margin-left : 5px;
  }

  .textBox{
    margin-top : 10px;
    grid-row : 3 / 4;
    grid-column : 2 / 3;
    
  }

  .textBox select ,.textBox input {
    padding-left : 5px;
    border:1px solid grey;
    margin : 15px 5px 5px 0px;
    height : 35px;
    width : 130px;
    background-color : rgb(224, 223, 223);
  }
  
</style>
