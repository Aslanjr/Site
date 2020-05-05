<template>
    <div class="Glasses">
        <div class="container-fuild">
            <div class="row">
                <div class="col-lg-3 p-0 d-flex flex-column align-items-center" v-for="(item,index) in Glasses" :key="index">
                    <div>
                        <img :src="item.src" height="230" alt="">
                    </div>
                    <p>
                        {{item.title}}
                    </p>
                    <div class="Glasses__Amount">
                        <p class="Glasses__Amount__item">add to cart</p>
                        <p class="Glasses__Amount__item">{{item.amount | Convert}}</p>
                    </div>
                </div>   
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Glasses',
    data(){
        return{

        }
    },
    methods:{

    },
    computed:{
        Glasses(){
            return this.$store.state.Products.Glasses;
        }
    },
    filters:{
        Convert(value){
            return   '$' + value ; 
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../../assets/mixins.scss';
    .Glasses{
        margin:3% 3%;
        &__Amount{
            overflow: hidden;
            display:flex;
            width:110px;
            height: 100%;
            @include title(14px,rgb(128,128,128));
            &__item{
                width:60px;
                height: 50px;
                transition:all .25s ease-in-out;
                transform: translateX(-40px);
            }
            &__item:nth-child(1){
                position: relative;
                right:30%;
                width:170px;
                cursor: pointer;
            }
        }
        &:hover &__Amount__item{
            transform: translateX(50px);
        }
    }
    
</style>