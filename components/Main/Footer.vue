<template>
    <div class="Footer">
        <div class="container-fuild">
            <div class="row">
                <div class="col-lg-3">
                    <p class="Footer__Logo">bazaar</p>
                    <p class="Footer__text">@Copyright Qode interactive</p>
                    <div class="d-flex">    
                        <div class="Footer__cards d-flex" v-for="(item,index) in Cards" :key="index">
                            <img :src="item.src" height="25" alt="">
                        </div>
                    </div>
                    <div class="d-flex">
                        <div class="Footer__social d-flex" v-for="(item,index) in SocialLinks" :key="index">
                            <img :src="item.src" height="25" alt="">
                        </div>
                    </div>
                </div>
                <div class="col-lg-3">
                    <p class="Footer__title">locate us</p>
                    <p class="Footer__text">28 Bartholomeo street, NY, NY</p>
                    <p class="Footer__text">phone: 0035 265 244 58</p>
                    <p class="Footer__text">phone: 0035 244 58 265</p>
                    <p class="Footer__text">e-mail: Ripasco@rambler.ru</p>
                </div>
                <div class="col-lg-3">
                    <p class="Footer__title">profile</p>
                    <p class="Footer__text">my account</p>
                    <p class="Footer__text">checkout</p>
                    <p class="Footer__text">order tracking</p>
                    <p class="Footer__text">help & support</p>
                </div>
                <div class="col-lg-3">
                    <div>
                        <input type="text" placeholder="e-mail" class="input">
                    </div>
                </div>
            </div>
        </div>        
    </div>
</template>
<script>
export default {
    name:'Footer',
    data(){
        return{
            Cards:[
                {
                    src:'/Cards/',
                },
                {
                    src:'/Cards/',
                },
                {
                    src:'/Cards/',
                },
                {
                    src:'/Cards/',
                },
                {
                    src:'/Cards/',
                },
            ],
            SocialLinks:[
                {
                    src:'/Social/',
                },
                {
                    src:'/Social/',
                },
                {
                    src:'/Social/',
                },
                {
                    src:'/Social/',
                },
                {
                    src:'/Social/',
                },
            ],
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../assets/mixins.scss';
    .Footer{
        padding: 3% 3%;
        color: #fff;
        background-color: #000;
        &__Logo{
            @include text(#fff,35px,0.03em,600);
            text-decoration: line-through;
        }
        &__title{
            @include text(#fff,25px,0.03em,500);
        }
        &__text{
            @include text(rgb(118,118,118),15px,0.05em,500);
        }
    }
</style>