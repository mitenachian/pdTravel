<template>
  <div>
    <Nuxt />
    <div class="scrolltoTop box_shadow" v-show="backFlag" @click="backTop()"><b-icon scale="2"  icon="arrow-up"></b-icon></div>
    <div class="social_med box_shadow">
         <div><a href="https://www.facebook.com/groups/OKASOS/" target="_blank"> <img src="@/assets/facebook_32.png"> </a></div>
         <div><a href="#" target="_blank"> <img src="@/assets//line_32.png"> </a></div>
         <div><a href="https://www.youtube.com/channel/UCQYtPx8eAiibthaLFwSPIxg" target="_blank"> <img src="@/assets/youtube_32.png"> </a></div>
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

  backTop(){ // 點擊返回頂部方法，計時器是為了過渡順滑 
  let that = this 
  let timer = setInterval(() => { let speed = Math.floor(-that.scrollTop /10) 
  //scrollTop獲取元素的滾動條的垂直位置，Math.floor() 向下取整 
  document.documentElement.scrollTop = document.body.scrollTop = that.scrollTop + speed 
  //document.documentElement.scrollTop 獲取當前頁面的滾動條縱坐標位置 
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
html {
  font-family: 'Noto Sans TC', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  overflow-x: hidden;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}


.scrolltoTop {
  position: fixed;
  right:20px;
  bottom:50px;
  width: 52px;
  height: 52px;
  line-height: 52px;
  background-color: #007bff;
  color: white;
  border-radius: 52px;
  cursor: pointer;
  text-align: center;
  z-index: 500;
}

.social_med div{
  padding: 9px  5px;
}
/*日曆的CSS*/

.day_box{
  height: 60px;
  width: auto;
}

.vc-day{
    border-bottom: 1px dashed #d9efff;
    border-right: 1px dashed #d9efff;
    font-size: 6px;
}
@media screen and (max-width: 480px) {
 .social_med{
  display: none;
  }
  .day_box div{
  margin:0;
}
}
@media screen and (min-width:1024px){
  .social_med{
  display: block;
  position: fixed;
  width: 52px;
  height: 150px;
  background-color: #c2dfff;
  border-radius: 20px;
  text-align: center;
  right:20px;
  bottom:120px;
  z-index: 500;
  }
  .day_box div{
  margin:5px;
}
}
</style>
