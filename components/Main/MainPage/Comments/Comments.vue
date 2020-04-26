<template>
    <div class="Comments">
        <div class="container-fuild">
            <div class="row d-flex justify-content-center">
                <div class="col-lg-12 d-flex flex-column align-items-center">
                    <div>
                        <p class="Comments__title">
                            what they’re saying
                        </p>
                    </div>
                    <div class="Comments__controls d-flex justify-content-between ">
                        <img src="https://image.flaticon.com/icons/svg/860/860790.svg" class="Comments__controls__img" height="24" alt="">
                        <img src="https://image.flaticon.com/icons/svg/318/318429.svg" class="Comments__controls__img" height="24" alt="">
                    </div>
                    <div class="Comments__Slider d-flex text-center ">
                        <FirstSlide v-if="FirstSlide" />
                        <SecondSlide v-if="SecondSlide" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import FirstSlide from './FirstComment'
import SecondSlide from './SecondComment'


export default {
    name:'Comments',
    data(){
        return{
            FirstSlide:true,
            SecondSlide:false
        }
    },
    methods: {
        SlideRight(){

        },
        SlideLeft(){
            
        }
    },
    components:{
        FirstSlide,
        SecondSlide
    }
}
</script>
<style lang="scss" scoped>
@import '../../../../assets/mixins.scss';

    .Comments{
        padding:3% 15%;
        &__title{
            @include text(#000,35px,0.03em,600);
        }
        &__Slider{
            padding:0% 20%;
        }
        &__controls{
            width:80%;
            position: absolute;
            top:45%;
            &__img{
                cursor:pointer;
                transition:all .45s ease;
                &:nth-child(1):hover{
                    transform: translateX(-10px);
                }
                &:nth-child(2):hover{
                    transform: translateX(10px);
                }
            }
        }
    }
</style>