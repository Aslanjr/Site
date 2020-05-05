<template>
    <div class="Video d-flex justify-content-center">
        <img src="interface.png" class="Video__controll" alt="">
    </div>
</template>
<script>
export default {
    name:'Video',
    data(){
        return{

        }
    }
}
</script>
<style lang="scss" scoped>
    .Video{
        padding:20% 0%;
        background-image: url('https://bazaar.qodeinteractive.com/wp-content/uploads/2017/06/h1-video-background-1.jpg');
        background-attachment: fixed;
        background-position: center center;
        &__controll{
            transition: all .5s  cubic-bezier(0,1.82,.88,1.65);
            cursor: pointer;
            &:hover{
                transform: scale(0.85);
            }
        }
        
    }
</style>