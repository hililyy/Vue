<template>
    <ItemAddRemoveForm
      :max_height = "200"
      :data = "data"
      :form = "form"
    />

<!--
      :add_disable = "add_disable"
      :remove_disable = "remove_disable"
      @change = "change"
      :title = '파일설정'
      :classes = "Object"
    -->

</template>

<script>
import ItemAddRemoveForm from '@/components/ItemAddRemoveForm.vue'

export default  { 
  data(){
    return {
        data: [],
        form : [{
            // form 1)
            field : 'key',  // 우리가 사용하는 부분..
            type : 'autocomplete',  //text, autocomplete만
            label : 'key',  // placeholder
        //     option : [{label : 'id', value : 'id'}], //autocomplete에서 사용하는 option-
        //  //   width : 400, 
        },
        
        { // form 2)
            field : 'value',
            type : 'text',
            label : 'value',
        }
      ],
    }
  },

  components : {
    ItemAddRemoveForm
  }
}
</script>