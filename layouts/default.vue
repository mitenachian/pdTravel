<template>
  <div>
    <Nuxt />
    <div class="scrolltoTop box_shadow" v-show="backFlag" @click="backTop()"><b-icon scale="2"  icon="arrow-up"></b-icon></div>
    <div class="social_med box_shadow">
         <div><a href="https://mitenachian.github.io/pdTravel/" target="_blank"> <img src="/facebook_32.png"> </a></div>
         <div><a href="https://mitenachian.github.io/pdTravel/" target="_blank"> <img src="/line_32.png"> </a></div>
         <div><a href="https://www.youtube.com/channel/UCQYtPx8eAiibthaLFwSPIxg" target="_blank"> <img src="/youtube_32.png"> </a></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      backFlag:false,
    }
  },
  mounted () { 
    window.addEventListener('scroll', this.showBtn) 
    //scroll 滾動事件 
  },
  methods:{ 
    showBtn () {
    let that = this 
    let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop 
    that.scrollTop = scrollTop 
    if (that.scrollTop > 40) { 
      let that = this 
      that.backFlag = true 
    } else { 
      that.backFlag = false
    }
  },

  backTop(){
  let that = this 
  let timer = setInterval(() => { let speed = Math.floor(-that.scrollTop /10)
  document.documentElement.scrollTop = document.body.scrollTop = that.scrollTop + speed 
  if (that.scrollTop === 0) { 
    clearInterval(timer) } 
    }, 20) 
  },
  },
  destroyed () { 
    // 銷毀監聽事件,當我們離開這個頁面的時候，便會調用這個函數 
    window.removeEventListener('scroll', this.showBtn) 
  },


}
</script>
<style>
</style>
