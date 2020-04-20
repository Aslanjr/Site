<template>
  <div class="Header">
      <div class="container-fuild Header__content">
        <div class="row justify-content-between align-items-start">
          <div class="col-lg-6">
            <div class="Logo text-left">
              <p class="Logo__Title">
                bazaar
              </p>
            </div>
          </div>
          <div class="col-lg-6 Menu flex-column d-flex justify-content-end">
            <div class="d-flex  Menu__content justify-content-around">
              <li class=" Menu__content__item" v-for="(item,index) in MenuList" :key="index" @mouseenter="show(item.title)">{{item.title}}
                <img src="" >
              </li>
            </div>
            <div class="dropdown   p-3 col-lg-3" v-show="homedrop" @mouseleave="close('Home')">
                <div class="dropdown__item" v-for="(item,index) in HomeDrop" :key="index"  >
                  <p>{{item.title}}</p>
                </div>
            </div>
            <div class="dropdown   p-3 col-lg-3" v-show="pagedrop" @mouseleave="close('Pages')">
                <div class="dropdown__item" v-for="(item,index) in PageDrop" :key="index"  >
                  <p>{{item.title}}</p>
                </div>
            </div>
            <div class="dropdown   p-3 col-lg-3" v-show="blogdrop" @mouseleave="close('Blog')">
                <div class="dropdown__item" v-for="(item,index) in BlogDrop" :key="index"  >
                  <p>{{item.title}}</p>
                </div>
            </div>
          </div>
        </div>
      </div>
      <section>
        <transition name="SwitchLeft">
          <FirstSlide  class="fb" :style="firstSlide" v-if="first" />
        </transition>
        <transition name="SwitchRight">
        <SecondSlide class="sc" :style="secondSlide" v-if="sec" />
        </transition>
        <transition name="SwitchLeft">
        <ThirdSlide  class="th" :style="thirdSlide" v-if="third"  />
        </transition>
      </section>
  </div>
</template>
<script>
import axios from 'axios'
import FirstSlide  from './MainPage/Slider/FirstSlide'
import SecondSlide from './MainPage/Slider/SecondSlide'
import ThirdSlide  from './MainPage/Slider/ThirdSlide'

export default {
  name:'LogForm',
  data:()=>{
    return{
      homedrop:false,
      pagedrop:false,
      blogdrop:false,
      first:true,
      sec:false,
      third:false,
      FirstIdx:1,
      SecondIdx:1,
      ThirdIdx:1,
    }
  },
  components:{
    FirstSlide,
    SecondSlide,
    ThirdSlide
  },
  mounted() {
    this.$on('slide', function(value){
        switch(value){
          case 1:
            //Show
            this.first = true;
            this.sec = false;
            this.third = false;
             //z-index
            this.FirstIdx = 2,
            this.SecondIdx = 1,
            this.ThirdIdx = 1
            break;
          case 2:
             //Show
            this.first = false;
            this.sec = true;
            this.third = false;
             //z-index
            this.SecondIdx = 2,
            this.FirstIdx = 1,
            this.ThirdIdx = 1
            break;
          case 3:
             //Show
            this.first = false;
            this.sec = false;
            this.third = true;
             //z-index
            this.ThirdIdx = 3,
            this.FirstIdx = 1,
            this.SecondIdx = 1
            break;
        }
      })
  },
  methods: {
      
    show(value){
      switch(value){
        case 'Home':
          this.homedrop = true;
          this.pagedrop = false;
          this.blogdrop = false;
          break;
        case 'Pages':
          this.homedrop = false;
          this.pagedrop = true
          this.blogdrop = false;
          break;
        case 'Blog':
          this.homedrop = false;
          this.pagedrop = false;
          this.blogdrop = true;
          break;
      }
    },
    close(value){
      switch(value){
        case 'Home':
          this.homedrop = false;
          break;
        case 'Pages':
          this.pagedrop = false;
          break;
        case 'Blog':
          this.blogdrop = false;
          break;
      }
    }
  },
  computed: {
    firstSlide(){
      return `z-index:${this.FirstIdx}`;
    },
    secondSlide(){
      return `z-index:${this.SecondIdx}`;
    },
    thirdSlide(){
      return `z-index:${this.ThirdIdx}`;
    },
    // eslint-disable-next-line vue/return-in-computed-property
    MenuList(){
      return this.$store.state.Header.Menu
      //Получаем массив названии для меню
    },
    HomeDrop(){
      return this.$store.state.Header.HomeDrop
      //Получаем массив названии для выподающего меню
    },
    PageDrop(){
      return this.$store.state.Header.PageDrop
      //Получаем массив названии для выподающего меню
    },
    BlogDrop(){
      return this.$store.state.Header.BlogDrop
      //Получаем массив названии для выподающего меню
    }
  },
}
</script>
<style lang="scss" scoped>

@import '../../assets/mixins.scss';
  .Header{
    padding:1% 4%;
    height:100vh;
    z-index: 6;
    transition: all 1s ease;
    .Header__content{
      position: relative;
      z-index: 5;
    }
  }
  .dropdown{
      background-color: #fff;
      position: relative;
      animation: Anime 0.40s ease-in-out;
      transform-origin:top;
      font-size: 14px;
      .dropdown__item{
          cursor: pointer;
          padding:0px 10px;
          transition: all 0.45s ease;
          &:hover{
            color:red;
          }
      }
  }
  .dropdown:nth-child(3){
    left:15%;
  }
  .dropdown:nth-child(4){
    left:45%;
  }
  @keyframes Anime{
    0%{
      transform: scaleY(0);
    }
    100%{
      transform: scaleY(1);
    }
  }
  .SwitchLeft-enter-active{
    animation: ShowLeft 1s ease;
  }
  .SwitchRight-enter-active{
    animation: ShowRight 1s ease;
  }
  @keyframes ShowLeft {
    0%{
      transform: translate(1920px);
    }
    100%{
      transform: translateX(0);
    }
  }
  @keyframes Close {
    0%{
      opacity: 0;
    }
    100%{
      opacity: 1;
    }
  }
  @keyframes ShowRight {
    0%{
      transform: translate(-1920px);
    }
    100%{
      transform: translateX(0);
    }
  }
  .Menu__content{
    list-style: none;
    color:#000;
    position: relative;
    .Menu__content__item{
      padding:3% 2%;
      cursor: pointer;
    }
  }
  .Logo{
    transition: all 1s ease;
    @include text(#000,25px,.01em,600);
    text-decoration: line-through;
  }
</style>

