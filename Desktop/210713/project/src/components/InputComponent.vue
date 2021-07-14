<template>
    <div id ="InputBox">
        <input id = "InputBoxkey" type ="text" v-model ="items.newkey" placeholder = "key">
        <input id = "InputBoxvalue" type ="text" v-model ="items.newvalue" placeholder = "value">
        <button id = "addButton" @click ="onClick">추가</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                items : [ 
                { newkey:'', newvalue: '' }
                ]
            }
        },
        methods :{
            onClick() {
                if(this.items.newkey !== "" && this.items.newvalue !==""){

                    var key = this.items.newkey && this.items.newkey.trim();
                    var value = this.items.newvalue && this.items.newvalue.trim();
                    
                    this.$emit('OnClick',key, value);
                    this.clearInput();
                }
            },
            clearInput(){
                this.items.newkey = '';
                this.items.newvalue = '';

            }
        }
    }
</script>

<style scoped>
    #InputBoxkey{
        width : 100px;
        height : 20px;
        margin-right: 10px;
        border-style : solid;
    }

    #InputBoxvalue{
        width : 150px;
        height : 20px;
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
</style>