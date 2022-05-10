<template>
    <div class="list-elements" v-if="elements.length>0">
         <transition-group name="transition-list">
            <element-item
                v-for="element in elements"
                :element="element"
                :key="element.id"
                @remove="$emit('remove',element)"
            />
         </transition-group>
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


<style scoped lang="scss">
    .list-elements{
        display: grid;
        grid-template: 1fr / repeat(3,1fr);
        grid-auto-flow: row;
        @media screen and (max-width:1340px) {
            flex-grow: 1;
            grid-template: 1fr / repeat(2,1fr);
            justify-content: center;
            justify-items: center;
        }
        @media screen and (max-width:1000px) {
            grid-template: 1fr / repeat(1,1fr); 
        }
    }
    .transition-list-item {
        display: inline-block;
        margin-right: 10px;
    }
    .transition-list-enter-active, .transition-list-leave-active {
        transition: all 0.4s;
    }
    .transition-list-enter, .transition-list-leave-to{
        opacity: 0;
        transform: translateY(-30px);
    }
    .transition-list-move {
    transition: transform 0.6s;
    }
</style>