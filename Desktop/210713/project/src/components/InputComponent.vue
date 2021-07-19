<template>
    <div id ="InputBox">
            <v-autocomplete>

            </v-autocomplete>
             <input 
                id = "InputBoxkey" 
                type ="text" 
                v-model ="data.newkey" 
                placeholder = "key"
            >
            <input 
                id = "InputBoxvalue" 
                type ="text" 
                v-model ="data.newvalue" 
                placeholder = "value"
            >
            <button id = "addButton" @click ="change">추가</button>
    </div>
</template>

<script>

    export default {
        components: {
           
        },
        data() {
            return {
                data : [ 
                { newkey:'', newvalue: '' } ],
            }
        },
        methods :{
            change() {
                if(this.data.newkey !== "" && this.data.newvalue !==""){
                    var key = this.data.newkey && this.data.newkey.trim();
                    var value = this.data.newvalue && this.data.newvalue.trim();
                    
                    this.$emit('change',key, value);
                    this.clearInput();
                }
            },
            clearInput(){
                this.data.newkey = '';
                this.data.newvalue = '';

            }
        }
    }
</script>

<style scoped>
    /* src="vue-advanced-search/dist/AdvancedSearch.css" */
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