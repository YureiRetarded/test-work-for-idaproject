<template>
    <div class="list-elements" v-if="elements.length>0">
        <element-item
            v-for="element in elements"
                :element="element"
                :key="element.id"
                @remove="$emit('remove',element)"
        />
    </div>
    <h2 v-else>Товары отсутствуют</h2>
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
        display: grid;
        grid-template: 1fr / repeat(3,1fr);
        grid-auto-flow: row;
    }
    @media screen and (max-width:1340px) {
        .list-elements{
            flex-grow: 1;
            grid-template: 1fr / repeat(2,1fr);
            justify-content: center;
            justify-items: center;
        }
    }
    @media screen and (max-width:1000px) {
        .list-elements{
            grid-template: 1fr / repeat(1,1fr); 
        }
    }
</style>