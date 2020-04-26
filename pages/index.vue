<template>
    <div>
      <Header/>
      <Products/>
      <ShopDiscont/>
      <Discont/>
      <Comments/>
    </div>
</template>

<script>
import Header       from '../components/Main/Header'
import Products     from '../components/Main/MainPage/Products'
import ShopDiscont  from '../components/Main/MainPage/Discont/ShopDiscont'
import Discont      from '../components/Main/MainPage/Discont/Discont'
import Comments     from '../components/Main/MainPage/Comments/Comments'

export default {
  components: {
    Header,
    Products,
    ShopDiscont,
    Discont,
    Comments
  }
}
</script>

<style>

</style>

