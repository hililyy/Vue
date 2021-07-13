<template>
    <div id ="InputBox">
        <input type ="text" v-model ="items.newkey" placeholder = "key">
        <input type ="text" v-model ="items.newvalue" placeholder = "value">
        <button @click ="onClick">추가</button>
    </div>
</template>

<script>
export default {
    // props:['keydata','valuedata'],
        
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
                
                //emit : 자식컴포넌트에서 부모컴포넌트로 보냄
                //props : 부모컴포넌트에서 자식컴포넌트로 보냄
                //규칙 : 전달 키와 받는 키가 동일해야한다.
                //       받는 키를 등록해줘야 한다.

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
