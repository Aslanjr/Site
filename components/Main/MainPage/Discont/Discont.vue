<template>
    <div class="ShopDiscont">
        <div class="container-fuild">
            <div class="row d-flex justify-content-end">
                <div class="col-lg-12 text-center">
                    <p class="ShopDiscont__title">shopping discont</p>
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
        background-image: url('https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-parallax-2.jpg');
        background-repeat: no-repeat;
        background-attachment: fixed;
        background-position-Y: 50%;
        &__title{
            @include title(135px,#000);
        }
    }
</style>