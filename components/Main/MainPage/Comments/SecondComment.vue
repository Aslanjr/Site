<template>
    <div >
        <div class="d-flex text-center">
            <div class="Comments__Slider__slide" >
                <p class="Comments__text">
                    Alliquam lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente, laboriosam,
                    ipsam laborum doloremque illo fuga voluptatum magni recusandae dicta, quisquam voluptatem reiciendis ab?
                    Pariatur non odio accusamus corporis nisi iure!
                </p>
                <p class="Comments__author">
                    Jennifer Jacobs
                </p>
                <p class="Comments__job">
                    Designer
                </p>                            
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Comments',
    data(){
        return{
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../../../assets/mixins.scss';

    .Comments__text{
        @include text(rgb(124, 124, 124),17px,0.02em,400);
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
    .Comments__author{
        @include text(#000,17px,0.02em,400);
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
    .Comments__job{
        @include text(rgb(124, 124, 124),17px,0.02em,400);
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

</style>