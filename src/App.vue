<template>
  
  <div class="app">
    <div class="title-block">
      <h1 class="title">Добавление товара</h1> 
      <my-select v-model="selectedSort" :options="sortOptions"></my-select>
    </div>
    <div class="elements">
      <element-form @create="createItem" />
      <element-list :elements="elements" @remove="removeElement"/>
    </div>
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
            {id:3,photo:'awdawd', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'666'},
            {id:4,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:5,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:6,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'10000'},
            {id:7,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'20'},
            {id:8,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'9'},
            {id:9,photo:'', element__name:'Наименование товара', element__description:'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', element__price:'9900000'},
        ],
        selectedSort:'',
        sortOptions:[
          {value:'element__name',name:"По наименованию"},
          {value:'min',name:"По убыванию цены"},
          {value:'max',name:"По возрастанию цены"},
        ],
      }
    },
    methods: {
      createItem(item){
        this.elements.push(item)
      },
      removeElement(element){
        this.elements = this.elements.filter(e=>e.id !== element.id)
      }
    },
    watch:{
      selectedSort(newValue){
          if(this.selectedSort=='min'){
            this.elements.sort((element1,element2)=>{return element2.element__price - element1.element__price})
          }
          else if(this.selectedSort=="max"){
            this.elements.sort((element1,element2)=>{return element1.element__price - element2.element__price})
          }
          else{
            this.elements.sort((element1,element2) => {return element1[this.selectedSort]?.localeCompare(element2[this.selectedSort])})
          } 
        }
    }
}
</script>

<style  lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  #app {
    padding: 32px;
    color: #3f3f3f;
  }
  .app{
    font-family: 'Open Sans', sans-serif;
    max-width: 1440px;
    min-height: 345px;
    margin: 0 auto;
    .title-block{
    display: flex;
    justify-content: space-between;
    padding: 0 16px;
  }
  }
  .app .title-block .title{
    font-size: 28px;
    font-weight: 600;
    font-stretch: normal;
    font-style: normal;
    line-height: normal;
    letter-spacing: normal;
    margin-bottom:16px;
  }
  .app .elements{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 0 16px;
  }
  @media screen and (max-width:660px) {
    .app .elements{
      flex-direction: column;
      align-items: center;
    }
    .app .title-block .title{
      text-align: center;
    }
  }
  @media screen and (max-width:530px) {
    .title-block{
      flex-direction: column;
      align-items: center;
    }
  }
</style>
