<template>
    <div class="list">
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


<style lang="scss" scoped>
    .list{
        margin: 0 16px;
        width: auto;
        display: grid;
        grid-template: 1fr / repeat(3,1fr);
        grid-auto-flow: row;
    }
</style>