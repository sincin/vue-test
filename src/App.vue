<template>
  <div >
    <Vheader :seller="seller"></Vheader>
    <div class="tab border-1px">
      <div class="tab-item">
        <a @click="$router.push('/goods')">商品</a>
      </div>
      <div class="tab-item">
        <a @click="$router.push('/ratings')">评论</a>
      </div>
      <div class="tab-item">
        <a @click="$router.push('/seller')">商家</a>
      </div>
    </div>
    <router-view  :seller="seller" keep-alive></router-view>
  </div>
</template>

<script>
import Vheader from 'components/header/header'
export default {
  data () {
    return {
      seller: {}
    }
  },
  components: {
    Vheader
  },
  created () {
    this.$http.get('/api/seller').then((response) => {
      this.seller = response.data.data
      console.log(this.seller)
    })
  }
}
</script>

<style  >
  .tab {
    display: flex;
    width: 100%;
    height: 40px;
    line-height: 40px ;
    border-bottom: 1px solid rgba(7, 17, 27, 0.1);
  }
  .tab-item{
    flex: 1;
    text-align: center
  }
  .tab-item a{
    font-size: 14px;
    display: block;
    color: rgb(77, 85, 93);
  }
  .tab-item a.active{
    color: rgb(240, 20, 20)
  }

</style>
