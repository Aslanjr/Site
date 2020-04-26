<template>
    <div class="ShopDiscont">
        <div class="container-fuild">
            <div class="row d-flex justify-content-end">
                <div class="col-lg-5 d-flex flex-column text-right">
                    <p class="ShopDiscont__discont">30%</p>
                    <p class="ShopDiscont__title">shopping everyday</p>
                    <div class="d-flex justify-content-end">
                        <p class="ShopDiscont__line"></p>
                    </div>
                    <div>
                        <button class="ShopDiscont__button">subscribe</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
@import "../../../../assets/mixins.scss";

    .ShopDiscont{
        padding:5% 15%;
        background-image: url(https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-parallax-1.jpg);
        background-repeat: no-repeat;
        background-attachment: fixed;
        background-position-Y: 100%;
        &__discont{
            @include title(135px,#000);
        }
        &__line{
            @include line(5px,70px,5%);
        }
        &__title{
            @include text(#000,35px,0.01em,500);
        }
        &__button{
            @include button(#fff,#000,17px);
            cursor: pointer;
            margin:10px 0px 0px 0px;
            transition:all 0.35s ease-in-out;
            &:hover{
                background:rgb(46, 46, 46);
            }
        }
    }
</style>