<template>
    <div class="Clothes">
        <div class="container-fuild">
            <div class="row align-items-center">
                <div class="col-lg-3 Clothes__item text-right  d-flex flex-column">
                    <p class="Clothes__item__title">that's it</p>
                    <p class="Clothes__item__text">copy the look</p>
                    <div class="d-flex justify-content-end">
                        <p class="Clothes__item__line"></p>
                    </div>
                    <p class="Clothes__item__text">
                        Alierewnum phaedrum torquatos nec <br> eu, dasvis detraxit ertssa periculiser <br> reex,nihil dexpetendis.
                    </p>
                </div>
                <div class="col-lg-9 p-0 d-flex Clothes__item">
                    <div class="col-lg-6 d-flex flex-wrap">
                        <div class="col-lg-12 Clothes__item__container">
                            <img src="https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-product-9.jpg" class="mainImg" alt="">
                            <div class="Clothes__item__info">
                                <p class="Clothes__item__info__title">{{Products[0].Category}}</p>
                                <p class="Clothes__item__info__text">{{Products[0].title}}</p>
                                <div class="d-flex">
                                    <p class="Clothes__item__info__title  mr-3"><strike>{{Products[0].OldAmount | dollar}}</strike></p>
                                    <p class="Clothes__item__info__title">{{Products[0].Amount | dollar}}</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-lg-12  justify-content-between d-flex">
                            <div class="Clothes__item__img  p-0 Clothes__item__container">
                                <img src="https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-product-11-550x550.jpg" class="img" height="250" alt="">
                                <div class="Clothes__item__info">
                                    <p class="Clothes__item__info__title">{{Products[1].Category}}</p>
                                    <p class="Clothes__item__info__text">{{Products[1].title}}</p>
                                    <div class="d-flex">
                                        <p class="Clothes__item__info__title  mr-3"><strike>{{Products[1].OldAmount | dollar}}</strike></p>
                                        <p class="Clothes__item__info__title">{{Products[1].Amount | dollar}}</p>
                                    </div>
                                </div>
                            </div>
                            <div class="Clothes__item__img  p-0 Clothes__item__container">
                                <img src="https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-product-12-550x550.jpg" class="img" alt="">
                                <div class="Clothes__item__info">
                                    <p class="Clothes__item__info__title">{{Products[2].Category}}</p>
                                    <p class="Clothes__item__info__text">{{Products[2].title}}</p>
                                    <div class="d-flex">
                                        <p class="Clothes__item__info__title  mr-3"><strike>{{Products[2].OldAmount | dollar}}</strike></p>
                                        <p class="Clothes__item__info__title">{{Products[2].Amount | dollar}}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-3  d-flex flex-column">
                        <div class="Clothes__item__container ">
                            <img src="https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-product-10-550x550.jpg" class="mainImg" alt="">
                            <div class="Clothes__item__info">
                                <p class="Clothes__item__info__title">{{Products[3].Category}}</p>
                                <p class="Clothes__item__info__text">{{Products[3].title}}</p>
                                <div class="d-flex">
                                    <p class="Clothes__item__info__title  mr-3"><strike>{{Products[3].OldAmount | dollar}}</strike></p>
                                    <p class="Clothes__item__info__title">{{Products[3].Amount | dollar}}</p>
                                </div>
                            </div>
                        </div>
                        <div class="Clothes__item__container">
                            <img src="https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-product-13-550x1100.jpg" class="img" alt="">
                            <div class="Clothes__item__info">
                                <p class="Clothes__item__info__title">{{Products[4].Category}}</p>
                                <p class="Clothes__item__info__text">{{Products[4].title}}</p>
                                <div class="d-flex">
                                    <p class="Clothes__item__info__title  mr-3"><strike>{{Products[4].OldAmount | dollar}}</strike></p>
                                    <p class="Clothes__item__info__title">{{Products[4].Amount | dollar}}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Clothes',
    data(){
        return{
            
        }
    },
    filters:{
        dollar(value){
            return '$'+value; 
        }
    },
    computed: {
        Products(){
            return this.$store.state.Products.FirstClothes
        },
    }
}
</script>
<style lang="scss" scoped>
@import '../../../assets/mixins.scss';

    .Clothes{
        overflow: hidden;
        padding:4% 0% 0% 10%;
        
        
        &__item__title{
            @include title(30px,rgb(158,158,158))
        }
        &__item__text{
            @include text(#000,30px,0.01em,600)
        }
        &__item__text:last-of-type{
            @include text(rgb(158,158,158),15px,0.01em,500)
        }
        &__item__line{
            @include line(4px,80px,20px);
        }
        &__item{
            &__container:hover  &__info{
                display: block;
            }
            &__container{
                flex-basis: 100%;
                position: relative;
                transition: all .45s ease;
                overflow: hidden;
            }
            &__img{
                flex-basis: 47%;
            }
            &__info{
                display: none;
                position:absolute;
                top:80px;
                left:60px;
                animation: Anime .45s ease-in-out;
                &__title{
                    margin: 0;
                    @include title(18px,#000(128,128,128));
                }
                &__text{
                    margin: 0;
                    @include text(#000,18px,0.01em,500);
                }
            }
        }
    }
    .mainImg{
        transition: all .45s ease-in-out;
        width: 100%;
        height: 95%;
    }
    .img{
        transition: all .45s ease-in-out;
        width:100%;
        height:100%;
    }
    @keyframes Anime {
        0%{
            opacity: 0;
            transform: translateY(30px);
        }
        100%{
            opacity: 1;
        }
    }
</style>