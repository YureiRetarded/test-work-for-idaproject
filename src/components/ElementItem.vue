<template >
    <div class="element-item">
        <div class="element-container">
            <img class="element-photo" :src="element.photo" @error="onImgLoadError">
            <div class="element-data">
                <span class="title">{{element.element__name}}</span>
                <span class="description">{{element.element__description}}</span>
                <div class="price"><span>{{decoratenumber(element.element__price)}}</span> руб.</div>
            </div>
             <div class="delete__button"><my-delete-button @click="$emit('remove',element)"></my-delete-button> </div>
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
            altimage:altimage,
            isActive:false
        }
    },
    methods: {
        onImgLoadError(e){
            e.target.src=altimage
        },
        decoratenumber(number){
            let reg = /(\d)(?=(\d\d\d)+([^\d]|$))/g
            let newNubmer = number.replace(reg,'$1 ');
            return newNubmer
        },
        isActiveToogle(){
            this.isActive = !this.isActive;
        }
    },

}
</script>


<style scoped lang="scss">
    .element-item{
        margin: 8px;
        width: 332px;
        height: 423px;
        border-radius: 4px;
        box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.02), 0 20px 30px 0 rgba(0, 0, 0, 0.04);
        background-color: #fffefb;
        .element-container {
            cursor: pointer;
            position: relative;
            width: 100%;
            height: 100%;
            .element-photo{
                border-radius:4px 4px 0 0;
                width: 332px;
                height: 200px;
            }
            .delete__button{
                position: absolute;
                top: -8px;
                right: -8px;
                transition: 0.5s;
                opacity: 0;
                visibility: hidden;
            }
            &:hover{
                .delete__button{
                    opacity: 1;
                    visibility: visible;
                }
            }
            .element-data{
                height: 223px;
                widows: 100%;
                padding: 16px 16px 24px 16px;
                display: flex;
                flex-direction: column;
                position: relative;
                .title{
                    font-size: 20px;
                    font-weight: 600;
                    font-style: normal;
                    line-height: normal;
                    letter-spacing: normal;
                    color: #3f3f3f;
                    margin-bottom: 16px;
                    justify-self: flex-start;
                }
                .description{
                    font-size: 16px;
                    font-weight: normal;
                    font-style: normal;
                    line-height: normal;
                    letter-spacing: normal;
                    color: #3f3f3f;
                }
                .price{
                    font-size: 24px;
                    font-weight: 600;
                    font-stretch: normal;
                    font-style: normal;
                    line-height: normal;
                    letter-spacing: normal;
                    color: #3f3f3f;
                    position: absolute;
                    bottom: 24px;
                    left: 16px;
                }
            }
        }
    }
</style>