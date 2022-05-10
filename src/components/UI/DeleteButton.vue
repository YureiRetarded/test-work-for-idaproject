<template >
   <button class="delete__btn">
        
    </button>
</template>
<script>
export default {
    name:'my-delete-button'
}
</script>
<style scoped>
    .delete__btn{
        cursor: pointer;
        width: 32px;
        height: 32px;
        border-radius: 10px;
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
        background-color: #ff8484;
        border: none;
        background-image: url(@/assest/trashbin.svg);
        background-position: center;
        background-repeat: no-repeat;
        padding: 5px;
        background-size: contain;
        background-origin:content-box ;
    }
</style>