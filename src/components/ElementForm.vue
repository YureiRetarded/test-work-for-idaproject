<template >
   <form @submit.prevent>
    <h4>Наименование товара</h4>
        <input v-model="item.element__name" type="text"  placeholder="Наименование товара">
        <h4>Описание товара</h4>
        <input v-model="item.element__description" type="text" placeholder="Описание товара">
        <h4>Ссылка на изображение товара</h4>
        <input v-model="item.element__photo" type="text" placeholder="Ссылка на изображение товара">
        <h4>Цена товара</h4>
        <input v-model="item.element__price" type="text" placeholder="Цена товара">
        <my-button @click="createItem">Добавить товар</my-button>
  </form>
</template>


<script>
export default {
    data() {
        return {
            item:{
                element__photo:'',
                element__name:'',
                element__description:'',
                element__price:''
            }
        }
    },
    methods: {
        createItem(){
            this.item.id=Date.now(),
            this.$emit('create',this.item),
            this.item={
                element__photo:'',
                element__description:'',
                element__name:'',
                element__price:''
            }
            
        }
    },
}
</script>


<style lang="scss">
    
</style>