<template>
    <div class="Events">
        <div class="container-fuild">
            <div class="row">
                <div class="col-lg-4 d-flex flex-column" v-for="(item,index) in Evetns" :key="index">
                    <p class="Events__date">{{item.date}}</p>
                    <p class="Events__title">{{item.title}}</p>
                    <p class="Events__text">{{item.text}}</p>
                    <p class="Events__link">learn more <img src="arrow.png" class="Events__link__img" alt=""></p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Events',
    data(){
        return{

        }
    },
    computed: {
        Evetns(){
            return this.$store.state.Events.Events
        }
    },

}
</script>
<style lang="scss" scoped>
@import '../../../assets/mixins.scss';
    
    .Events{
        margin: 100px 0px;
        background-color: #FAFAFA;
        padding: 3% 15%;
        &__date{
            @include title(17px,rgb(128,128,128));
        }
        &__title{
            @include text(#000,22px,0.01em,600);
        }
        &__text{
            @include text(rgb(178,178,178),16px,0.01em,500);
        }
        &__link{
            @include title(20px,#000);
            cursor: pointer;
            &__img{
                transition: all .25s ease-in-out;
            }
            
            &:hover &__img{ 
                transform: translateX(15px);
            }
        }
    }
</style>