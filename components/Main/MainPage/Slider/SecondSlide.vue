<template>
    <div class="FirstSlide">
        <div class="conainer-fuild">
            <div class="row  d-flex">
                <div class="col-lg-12 mt-5 FirstSlide__item text-left">
                    <h1 class="FirstSlide__item__title">perfect <br> time to shop</h1>
                    <div class="d-flex justify-content-start">
                        <p class="line"></p>
                    </div>
                    <p class="FirstSlide__item__text">
                        Alienum phaedrum torquatos nec eu, vis detraxit ortssa
                        periculiser ex, <br> nihil expetendis in mein redsal ubunt. 
                    </p>
                    <button class="button">subscribe</button>
                </div>
                <div class="col-lg-12 FirstSlide__item__controls d-flex justify-content-between">
                    <div class="FirstSlide__item__left d-flex justify-content-center" @click="Slide(1)">
                        <div class="arrow d-flex flex-column justify-content-center align-items-center">
                            <div></div>
                            <div></div>
                        </div>
                        01
                    </div>
                    <div class="FirstSlide__item__right d-flex " @click="Slide(3)">
                        03
                        <div class="arrow d-flex flex-column justify-content-center align-items-center">
                            <div></div>
                            <div></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'FirstSlide',
    data(){
        return{
            
        }
    },
    methods: {
        Slide(value){
            if(value == 1){
                this.$parent.$emit('slide',value);
            }else if( value == 3){
                this.$parent.$emit('slide',value);
            }else{
                console.log('error');
            }
        }
    },     
}
</script>
<style lang="scss" scoped>
@import '../../../../assets/mixins.scss';
    .FirstSlide{
        @include Slide('https://bazaar.qodeinteractive.com/wp-content/uploads/2017/07/h1-slider1-background-img.jpg');
        .FirstSlide__item__controls{
            position: absolute;
            top:50%;
            left:0%;
            padding:0% 2%;
            cursor:pointer;
            font-size: 30px;
            .FirstSlide__item__left{
                font-weight: 600;
                .arrow{
                    height: 50px;
                    width: 50px;
                }
                .arrow div:first-of-type{
                    @include arrow(top);
                }
                .arrow div:last-of-type{
                    @include arrow(bottom);
                }
                &:hover{
                    .arrow div:first-of-type{
                        transform: rotate(45deg) translateY(6.5px);
                    }
                    .arrow div:last-of-type{
                        transform: rotate(-45deg)translateY(-6.5px);
                    }
                }
            }
            .FirstSlide__item__right{
                font-weight: 600;
                .arrow{
                    height: 50px;
                    width: 50px;
                }
                .arrow div:first-of-type{
                    @include arrow(top);
                }
                .arrow div:last-of-type{
                    @include arrow(bottom);
                }
                &:hover{
                    .arrow div:first-of-type{
                        transform: rotate(-45deg) translateY(6.5px);
                    }
                    .arrow div:last-of-type{
                        transform: rotate(45deg)translateY(-6.5px);
                    }
                }
            }
            
        }
        .line{
            @include line(7px,120px,35px);
        }
        .FirstSlide__item{
            animation: ShowUp 1.8s ease;
            padding: 0% 15%;
            position: absolute;
            top:30%;
            left:0%;
            .FirstSlide__item__title{
                @include text(#000,75px,0.02em,600);
            }
            .FirstSlide__item__text{
                @include text(rgb(132,132,132),16px,0.02em,500);
            }
            .button{
                margin:30px 0px 0px 0px;
                @include button(#fff,#000,16px)
            }
        }
        @keyframes ShowUp {
            0%{
                opacity: 0;
                transform: translateY(-60px);
            }
            100%{
                opacity: 1;
            }
        }
    }
</style>
