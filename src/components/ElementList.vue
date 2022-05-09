<template>
    <div class="list-elements">
        <element-item
            v-for="element in elements"
                :element="element"
                :key="element.id"
        />
    </div>
</template>


<script>
import ElementItem from './ElementItem'
export default {
    components:{
        ElementItem
    },
    props:{
        elements:{
            type:Array,
            required:true
        }
    }
}
</script>


<style scoped>
    .list-elements{
        margin: 0 16px;
        width: auto;
        display: grid;
        grid-template: 1fr / repeat(3,1fr);
        grid-auto-flow: row;
    }
    @media screen and (max-width:1340px) {
        .list-elements{
            grid-template: 1fr / repeat(2,1fr); 
        }
    }
    @media screen and (max-width:1000px) {
        .list-elements{
            grid-template: 1fr / repeat(1,1fr); 
        }
    }
</style>