<template>
      <div class = "Setting">
        <ul class = "title">
            <label>접속 정보</label>
        </ul>
        <ul class ="menu">
            <label>접속방식</label>
            <label>key</label>
            <label>value</label>
          </ul>
        
        <div class = "element">
              <ul class = "RadioButton"> 
                <li v-for = "(option,index) in ConnectOption" v-bind:key = "index">
                  <input type = "radio" name="radio">
                  <label for = option>{{option}}</label>
                </li>
              </ul>
        
        <div class = "InputBox">
          <ul v-for="(n,index) in 3" v-bind:key="index">
              <select v-model="selectExcludes[n-1]" class="select">
                  <option v-for = "(item,index) in InputOption" v-bind:key = "index" :disabled="isVisible(item.index)" :value="item.index">
                    {{item.id}}
                  </option>
              </select>
              <span v-if = "selectExcludes[n-1] == '1'">
                  <input type = "password">
              </span>
              <span v-else>
                  <input type = "text">
              </span>
              
          </ul>
        </div>

        </div>
      </div>

</template>

<script>
export default  {
    data() {
      return {
        InputOption : [
          {id : "Port", index : 0 },
          {id : "Password", index : 1 },
          {id : "API", index : 2 },
          {id : "Secret", index : 3 },
          {id : "Access", index : 4 }
          ],
        selectExcludes: [],
        ConnectOption : ["SSH","API","HMAC","GUI"],
      }
    },
    methods: {
      isVisible (data) { 
        let returnFlag = false 
        for (const i in this.selectExcludes) { 
          if (this.selectExcludes[i] === data) { 
            returnFlag = true 
          }
        }
          return returnFlag 
      },

      dataCheck () { 
        console.log(this.selectExcludes) 
      },

      setFirstData () { 
        this.$set(this.selectExcludes, 0, '111') 
      }
    }
}
  
</script>

<style scoped>
  .menu { 
     border:1px solid grey;
     border-top-width : 0px;
     border-bottom-width : 0px;
     padding-top :20px;
  }
  .menu label{
    margin : 0px 70px 0px 35px;
  }
  .InputBox{
    width : 300px;
    display : inline;
    margin-top : 10px;
  }
  .InputBox li {
    list-style: none;
  }
  .InputBox ul {
    margin-top : 10px;
  }
  .InputBox select ,.InputBox input {
    border:1px solid grey;
    margin : 5px 5px 5px 0px;
    height : 35px;
    width : 130px;
  }
  .RadioButton {
    width : 100px;
    margin : 10px 60px 0px 20px;
    
    
  }
  .RadioButton li {
    margin : 20px 0px 10px 10px;
    list-style: none;
    
    width : 70px;
    
  }

  .RadioButton label{
    margin-right : 3px;
  }

  .title li { 
    padding-left:0px;
    display : inline;
    list-style : none;
    
  }

  .title {
    padding : 10px 0px 10px 10px;
    margin-bottom : 0; 
    border:1px solid grey;
    height : 40px;
  }

  .element { 
    padding : 0px 0px 0px 10px;
        border:1px solid grey;
        border-top-width : 0px;
        height : 200px;
        width : 500px;
        display : flex;
        flex-wrap: wrap;
        
  }
  .Setting { 
    width : 500px;
    margin : 20px 20px 40px 20px;
  }

  .Setting input {
    margin-right : 5px;
  }

</style>
