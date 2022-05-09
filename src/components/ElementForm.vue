<template >
   <form class="element-form" @submit.prevent>
       <div class="block">
           <h4>Наименование товара</h4>
            <input class="input" v-model="item.element__name" type="text"  placeholder="Наименование товара">
       </div>
       <div class="block">
            <h4>Описание товара</h4>
            <textarea  class="input"  v-model="item.element__description" placeholder="Описание товара"></textarea>
            <!-- <input class="input" v-model="item.element__description" type="textarea" placeholder="Описание товара"> -->
       </div>
       <div class="block">
            <h4>Ссылка на изображение товара</h4>
            <input class="input" v-model="item.photo" type="text" placeholder="Ссылка на изображение товара">
       </div>
       <div class="block">
            <h4>Цена товара</h4>
            <input class="input" v-model="item.element__price" type="text" placeholder="Цена товара">
       </div>
        <my-button @click="createItem">Добавить товар</my-button>
  </form>
</template>


<script>
export default {
    data() {
        return {
            item:{
                photo:'',
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
                photo:'',
                element__description:'',
                element__name:'',
                element__price:''
            }
            
        }
    },
}
</script>


<style lang="scss">
    .element-form{
        width:322px ;
        height:440px ;
        padding: 24px;
        border-radius: 4px;
        box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.02), 0 20px 30px 0 rgba(0, 0, 0, 0.04);
        background-color: #fffefb;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        .block{
            h4{
            font-size: 10px;
            font-weight: 600;
            font-stretch: normal;
            font-style: normal;
            line-height: normal;
            letter-spacing: -0.2px;
            color: #49485e;
            margin-bottom: 4px;
        }
            .input{
                border-radius: 4px;
                box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.1);
                border: none;
                background-color: #fffefb;
                width: 100%;
                height: 36px;
                padding: 10px 16px 10px 16px;
                font-size: 12px;
                color: #3f3f3f;
                &:focus{
                    outline: none
                }
                &::placeholder{
                    font-size: 12px;
                    font-weight: normal;
                    font-style: normal;
                    line-height: normal;
                    letter-spacing: normal;
                    color: #b4b4b4;
                }
            }
        }
        .block:nth-child(2){
            .input{
                height: 108px;
                resize: none;
            }
        }
    }
</style>