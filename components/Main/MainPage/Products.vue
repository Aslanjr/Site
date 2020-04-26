<template>
    <div class="Products">
        <div class="container-fuild">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <p class="Content__title m-0">don’t wait</p>
                    <p class="Content__name m-0">shopping everyday</p>
                    <div class="d-flex justify-content-center">
                        <p class="line"></p>
                    </div>
                    <p class="Content__text m-0">
                        Alienum phaedrum torquatos nec eu, vis detraxit ertssa periculiser ex, nihil <br>
                         expetendis in meinerst gers frust bura erbu
                    </p>
                    <div class="justify-content-around d-flex flex-wrap mt-5">
                        <div class="col-md-3 Product__info d-flex flex-column" @mouseenter="ToogleInfo" @mouseleave="CloseInfo"  v-for="(item,index) in Products" :key="index">
                            <div class="d-flex flex-column align-items-center">
                                <img :src="item.Img" height="325" alt="">
                                <transition name="switch">
                                    <div class="ImgInfo ">
                                        <div class="ImgInfo__title align-items-center d-flex justify-content-center">
                                            <p>quick look</p>
                                        </div>
                                        <div class="ImgInfo__Icon d-flex align-items-center justify-content-center">
                                            <img :src="item.Icon" height="15" alt="">
                                        </div>
                                    </div>
                                </transition>
                            </div>
                            <div class="d-flex justify-content-between align-items-end">
                                <div class="d-flex flex-column">
                                    <p class="ProductName">{{item.Title}}</p>
                                    <p class="text-left ProductCategory">{{item.Category}}</p>
                                </div>
                                <div class="d-flex">
                                    <p class="Cart">add to cart <img src="../../../static/arrow.png" height="13" alt=""> </p>
                                    <p class="Amount">{{item.Amount | dollar}}</p>
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
    name:'',
    data(){
        return{
            Product__Cart:false,
            Product__Amount:true,
        }
    },
    methods: {
        ToogleInfo(){
            this.Product__Amount = false;
            this.Product__Cart = true;
        },
        CloseInfo(){
            this.Product__Amount = true;
            this.Product__Cart = false;
        }
    },
    filters:{
        dollar(value){
            return '$' + value;
        }
    },
    computed: {
        Products(){
            return this.$store.state.Products.Products;
        }
    },
}
</script>
<style lang="scss" scoped>
@import '../../../assets/mixins.scss';
    .Products{
        margin: 5% 13%;
        overflow: hidden;
    }
    .Product__info{
        margin:40px 0px;
    }
    .ImgInfo{
        display:none;
        position:absolute;
        bottom:15%;
        padding:10px;
        &__title{
            height:25px;
            width:80px;
            background-color: #000;
            cursor: pointer;
            @include text(#fff,12px,0.01em,500);
            p{
                margin:0;
            }
        }
        &__Icon{
            height:25px;
            width:30px;
            cursor: pointer;
            background-color: grey;
            transition:all .3s ease-in-out;
            &:hover{
                background:#fff;
            }
        }
    }
    .Content__title{
        @include title(35px,rgb(173, 171, 171));
    }
    .Product__info:hover .Cart{
        display:block;
        animation:Anime .55s ease;
    }
    .Product__info:hover .Amount{
        display:none;
    }
    .Product__info:hover .ImgInfo{
        display:flex;
        animation:Animated 1s ease;
    }
    .Cart{
        display:none;
        cursor:pointer;
        @include text(rgb(160, 160, 160),13px,0.01em,500);
    }
    .ProductName{
        margin: 15px 0px 3px 0px;
        @include text(#000,16px,0.01em,500)
    }
    .ProductCategory{
        margin: 0;
        @include title(14px,rgb(173, 171, 171));
    }
    .Content__name{
        @include text(#000,35px,0.01em,500)
    }
    .Content__text{
        @include text(rgb(110, 110, 110),17px,0.05em,500)
    }
    .line{
        @include line(5px,80px,20px);
    } 
    @keyframes Animated {
        0%{
            opacity: 6;
            transform: translateY(5px);
        }
        100%{
            opacity: 1;
        }
    }
    @keyframes Anime {
        0%{
            opacity: 6;
            transform: translateX(-35px);
        }
        100%{
            opacity: 1;
        }
    }   
</style>