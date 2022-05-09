<template >
    <div>
        {{element.id}}
        {{element.photo}}
        {{element.element__name}}
        {{element.element__description}}
        {{element.element__price}}
    </div>
</template>


<script>
export default {
    props:{
        element:{
            type:Object,
            required:true
        }
    }
}
</script>


<style lang="scss">
    
</style>