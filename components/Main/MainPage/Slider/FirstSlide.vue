<template>
    <div class="FirstSlide">
        <div class="conainer-fuild">
            <div class="row  d-flex">
                <div class="col-lg-12 FirstSlide__item text-right">
                    <h1 class="FirstSlide__item__title">sense of <br> sophistication</h1>
                    <p class="line"></p>
                    <p class="FirstSlide__item__text">
                        Alienum phaedrum torquatos nec eu, vis detraxit ortssa
                        periculiser ex, <br> nihil expetendis in mein redsal ubunt. 
                    </p>
                    <button class="button">subscribe</button>
                </div>
                <div class="col-lg-12 FirstSlide__item__controls d-flex justify-content-between">
                    <div class="FirstSlide__item__left">
                        <svg>
                            <polyline points="40,0 26,15 39,29" fill="rgb(231,231,229)" stroke-width="3" stroke="rgb(0,0,0)"/>
                        </svg>
                        1
                    </div>
                    <div class="FirstSlide__item__right">2</div>
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
    }    
}
</script>
<style lang="scss" scoped>
@import '../../../../assets/mixins.scss';
    .FirstSlide{
        position: absolute;
        top:0%;
        left:0%;
        height:100%;
        width: 100%;
        background:url('https://bazaar.qodeinteractive.com/wp-content/uploads/2017/07/h1-slider2-background-img.jpg');
        background-attachment: fixed;
        .FirstSlide__item__controls{
            position: absolute;
            top:50%;
            left:0%;
            padding:0% 2%;
            font-size: 30px;
            .FirstSlide__item__left{
                svg{
                    width: 105px;
                    height: 130px;
                }
            }
        }
        .FirstSlide__item{
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
    }
</style>
