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
<style lang="scss" scoped>
    .btn{
    padding: 10px;
    background: none;
    color: black;
    border: 1px solid wheat;
    border-radius: 5px;
}
</style>