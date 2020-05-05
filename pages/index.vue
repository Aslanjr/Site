<template>
    <div class="Main">
      <Header/>
      <Products/>
      <ShopDiscont/>
      <Discont/>
      <Comments/>
      <Glasses/>
      <Video/>
      <Clothes/>
      <Events/>
      <Footer/>
    </div>
</template>

<script>
import Header       from '../components/Main/Header'
import Products     from '../components/Main/MainPage/Products'
import ShopDiscont  from '../components/Main/MainPage/Discont/ShopDiscont'
import Discont      from '../components/Main/MainPage/Discont/Discont'
import Comments     from '../components/Main/MainPage/Comments/Comments'
import Glasses      from '../components/Main/MainPage/Glasses'
import Video        from '../components/Main/MainPage/Video'  
import Clothes      from '../components/Main/MainPage/Clothes'
import Events       from '../components/Main/MainPage/Events'
import Footer       from '../components/Main/Footer'

export default {
  components: {
    Header,
    Products,
    ShopDiscont,
    Discont,
    Comments,
    Glasses,
    Video,
    Clothes,
    Events,
    Footer
  }
}
</script>

<style scoped>
  .Main{
    overflow: hidden;
    width: 100%;
  }
</style>

