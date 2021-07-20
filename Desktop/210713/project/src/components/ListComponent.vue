<template>
    <section>
        <ul id ="list">
            <li v-for="(item, index) in data" v-bind:key="index">
                <input id = "keyInputBox" type ="text" v-model ="item.keys">
                <input id = "valueInputBox" type ="text" v-model ="item.values">
                <button id ="removeButton" @click="OnRemove(item,index)">제거</button>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props : {
        data : Array,
    },
    methods : {
        OnRemove(item, index){
            this.$emit('OnRemove', item, index);
        }
    },
}
</script>
<style scoped>
    #list {
        list-style:none;
        padding-left:0px;
    }

    #keyInputBox{
        width : 100px;
        height : 26px;
        margin : 0px 10px 0px 0px;
        border-style : solid;
    }

    #valueInputBox{
        width : 150px;
        height : 26px;
        margin : 0px 10px 0px 0px;
        border-style : solid;
    }
    #removeButton {
        width : 50px;
        height : 26px;
        margin : 0px;
        border-style : solid;
        border-color :rgb(215, 205, 219);
        background-color :#ffd4d4;
    }
    li{
        margin-top : 15px;
    }


</style>
