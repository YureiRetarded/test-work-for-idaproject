<template>
    <div>
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


<style lang="scss">
    
</style>