<template >
    <div class="element-item">
        <div class="element-container">
            <img class="element-photo" :src="element.photo" @load="onImgLoad" @error="onImgLoadError">
            <div class="element-data">
                {{element.id}}
                {{element.element__name}}
                {{element.element__description}}
                {{element.element__price}}
            </div>
        </div>

       
        
        
    </div>
</template>


<script>
import altimage from '@/assest/element-item-alt.png'
export default {
    props:{
        element:{
            type:Object,
            required:true
        }
    },
    data() {
        return {
            isLoaded:false,
            altimage:altimage
        }
    },
    methods: {
        onImgLoad(){
            this.isLoaded=true
        },
        onImgLoadError(){
            this.element.photo=altimage
        }
    },

}
</script>


<style lang="scss">
    .element-item{
        border: 1px solid black;
        margin: 5px;
        padding: 5px;
        .element-container{
            .element-photo{
                width: 322px;
                height: 200px;
                
            }
        }
    }
</style>