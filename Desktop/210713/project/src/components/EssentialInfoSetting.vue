<template>
    <div class = "Setting">
        <ul class = "menu">
            <label>필수 정보</label>
        </ul>
        <div class = "element">
            <ul class = "ElementOption" v-for = "(option,index) in Option" v-bind:key="index">
                <li>{{option}}</li>
                <input type="text">
            </ul>
        </div>        
    </div>
</template>

<script>
export default {
   data(){
       return{
           Option : ["IP 주소","호스트 이름","장비 이름","모델 이름"],
       }
    }
}
</script>
<style scoped>
    .element{
        padding : 15px 0px 0px 10px;
        border:1px solid grey;
        border-top-width : 0px;
        height : 120px;
        width : 500px;
        flex-wrap: wrap;
        
    }
    .ElementOption{
        display : inline-block;
    }
    .ElementOption li {
        margin : 10px 0px 10px 20px;
        text-align: left;
        list-style: none;
        display : inline;
        float : left;
        width : 80px;
        
    }
    .ElementOption input{
        border:1px solid grey;
        margin : 5px 10px 5px 0px;
        width : 110px;
        height : 30px;
        float : right;
    }
    .menu {
        padding : 10px 0px 10px 10px;
        margin-bottom : 0; 
        border:1px solid grey;
        height : 40px;
    }
    .menu li { 
        padding-left:0px;
        display : inline;
        list-style:none;
    }
    .Setting { 
    width : 500px;
    margin : 20px 20px 40px 20px;
  }
</style>