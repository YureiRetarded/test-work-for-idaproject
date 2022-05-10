<template >
    <button class="btn">
        <slot></slot>
    </button>
</template>
<script>
export default {
    name: 'my-button'
}
</script>
<style scoped lang="scss">
    .btn{
        padding: 10px;
        background: none;
        color: #fff;
        border-radius: 10px;
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
        background-color: #7bae73;
        border: none;
        transition: 0.5s;
        &:hover{
            cursor: pointer;
            background-color: #759970;
        }
    }
</style>