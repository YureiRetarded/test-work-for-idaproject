<template >
   <button class="delete__btn">
        <slot></slot>
    </button>
</template>
<script>
export default {
    name:'my-delete-button'
}
</script>
<style scoped>
    .delete__btn{
        background-color: aqua;
    }
</style>