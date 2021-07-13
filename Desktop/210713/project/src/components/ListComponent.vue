<template>
    <section>
        <ul>
           <li v-for="(item, index) in items" :key="index">
            {{ items.key }} {{ items.value }} 
            <button @click="OnRemove(item,index)">제거</button>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props : [
        // 'key' : string, 
        // 'value' : string 
        'key','value'
    ],
    created(){
        console.log("1");
        
    },
    methods : {
        OnRemove(items,index){
            this.$emit('OnRemove',items,index);
        }
    }
}
</script>
