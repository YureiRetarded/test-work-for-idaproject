<template>
<div>
  <element-form>

  </element-form>
  <element-list :elements="elements">

  </element-list>
</div>
</template>


<script>
import ElementList from '@/components/ElementList'
import ElementForm from '@/components/ElementForm'
export default {
    components:{
      ElementList,
      ElementForm

    },
    data() {
      return {
        elements:[
            {id:1,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:2,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:3,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:4,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:5,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:6,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:7,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:8,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:9,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
        ],
        
      }
    },
}
</script>


<style>

</style>
