<template>
    <div id ="InputBox">
            <input 
                id = "InputBoxkey" 
                type ="text" 
                v-model ="newdata.newkey" 
                placeholder = "key"
                list ="keylist"
            />

            <datalist id = "keylist">
                <option v-for="(item, index) in form[0].option" v-bind:key="index" >{{item}}</option>
            </datalist>
            
            <input 
                id = "InputBoxvalue" 
                type ="text" 
                v-model ="newdata.newvalue" 
                placeholder = "value"
            /> 
            <button id = "addButton" @click ="change">추가</button>
    </div>
</template>

<script>

    export default {
        props : {
            data : Array,
            form : Array,
        },

        data() {
            return {
                newdata : [ 
                { newkey:'', newvalue: '' } ],
            }
        },
        
        methods :{
            
            change() {                
                if(this.add_disable()){
                    var key = this.newdata.newkey && this.newdata.newkey.trim();
                    var value = this.newdata.newvalue && this.newdata.newvalue.trim();
                    
                    this.$emit('change',key, value);
                    this.clearInput();
                }
            },
            clearInput(){
                this.newdata.newkey = '';
                this.newdata.newvalue = '';
            },
            add_disable () {
                if(this.newdata.newkey !== "" && this.newdata.newvalue !== "")
                    return true;
            },
        }
    }
</script>

<style scoped>
    #InputBox{
        margin-top:15px;
    }
    #InputBoxkey{
        width : 100px;
        height : 26px;
        margin-right: 10px;
        border-style : solid;
    }

    #InputBoxvalue{
        width : 150px;
        height : 26px;
        margin-right: 10px;
        border-style : solid;
    }

    #addButton{
        width : 50px;
        height : 26px;
        margin : 0px;
        border-style : solid;
        border-color :rgb(173, 182, 190);
        background-color :rgb(225, 235, 255);
    }
    input {
        padding-left : 5px;
    }
</style>