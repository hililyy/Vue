<template>
    <ItemAddRemoveForm
      :max_height = "200"
      :data = "data"
      :form = "form"
    />

<!--
      :title = "파일 설정"
      :add_disable = "add_disable"
      :remove_disable = "remove_disable"
      @change = "change"
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
            field : 'key',  // 우리가 사용하는 부분
            type : 'autocomplete',  //text, autocomplete만
            label : 'key',  // placeholder
            option : [], //autocomplete에서 사용하는 option-
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
  methods : {
    
  },
  components : {
    ItemAddRemoveForm
  }
}
</script>