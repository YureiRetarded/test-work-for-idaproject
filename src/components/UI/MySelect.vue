<template>
    <select class="selection" v-model="modelValue" @change="changeOption">
        <option disabled value="">По умолчанию</option>
        <option :value="option.value" v-for="option in options" :key="option.value"> {{option.name}}</option>
    </select>
</template>
<script>
export default {
    name: 'my-select',
    props:{
        modelValue:{
            type:String
        },
        options:{
            type:Array,
            default:()=>[]
        }
    },
    methods: {
        changeOption(event){
            this.$emit('update:modelValue',event.target.value)
        }
    },
}
</script>
<style scoped >
    .selection{
        border-radius: 4px;
        box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.1);
        background-color: #fffefb;
        height: 36px;
        border: none;
    }
</style>