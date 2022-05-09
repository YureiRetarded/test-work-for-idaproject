<template>
  <div>
    <element-form @create="createItem" />
    <element-list :elements="elements"/>
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
            {id:1,photo:'https://www.planetware.com/wpimages/2020/02/france-in-pictures-beautiful-places-to-photograph-eiffel-tower.jpg', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:2,photo:'https://www.planetware.com/wpimages/битая-ссылка/ctures-beautiful-places-to-photogr', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
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
    methods: {
      createItem(item){
        this.elements.push(item)
      }

    },
}
</script>


<style>

</style>
