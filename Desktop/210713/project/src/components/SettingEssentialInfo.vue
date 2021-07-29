<template>
    <div class = "setting">
        <div class = "title">
            <label>필수 정보</label>
        </div>
        <div class = "element">
            <div class = "elementItem" 
                v-for = "(item,index) in item" 
                v-bind:key="index" 
            >
                <label>{{item.key}}</label>
                <input 
                    type="text" 
                    v-model = "item.value" 
                    disabled
                />
            </div>
        </div>        
    </div>
</template>

<script>
export default {
    created(){
        if(this.datalist.ip!=undefined){
            this.item.push(
                { key : "IP 주소", 
                  value : this.datalist.ip },
                { key : "호스트 이름", 
                  value : this.datalist.host },
                { key : "장비 이름", 
                  value : this.datalist.equip },
                { key : "모델 이름", 
                  value : this.datalist.model },
            )
        }
        else {
            this.item.push(
                { key : "IP 주소", 
                  value : "" },
                { key : "호스트 이름", 
                  value : "" },
                { key : "장비 이름", 
                  value : "" },
                { key : "모델 이름", 
                  value : "" },
            )
        }
    },
    props : {
      datalist : Object
    },
   data(){
       return{
           item : []
       }
    }
}
</script>
<style scoped>
    .setting { 
        margin : 20px 20px 40px 20px;
        border:1px solid grey;
        grid-template-rows: 40px 130px;
        grid-template-columns: 1fr;
        display : grid;
    }

    .title {
            padding : 10px 0px 10px 10px;
            border: solid grey; 
            border-width : 0px 0px 1px 0px;
            grid-column : 1 / 2;
            grid-row : 1 / 2;   
        }

    .element{
        padding : 15px 0px 0px 10px;
        height : 120px;
        width : 490px; 
        grid-column : 1 / 2;
        grid-row : 2 / 3;
    }

    .elementItem{
        display : inline-block;
    }

    .elementItem label {
        margin : 10px 0px 10px 20px;
        float : left;
        width : 80px;
    }
    .elementItem input{
        border:1px solid grey;
        margin : 5px 10px 5px 0px;
        width : 120px;
        height : 30px;
        float : right;
        padding-left : 5px;
        background-color : rgb(224, 223, 223);
    }
    
</style>