<template>
  <div id="footer">
    <div id="bottom_link">
      <li><a href="#">關於彭大家族</a></li>
      <li><a href="#">品牌理念</a></li>
      <li><a href="#">付款取貨</a></li>
      <li><a href="#">隱私權保護</a></li>
      <li><a href="#">交易安全</a></li>
      <li><a href="#">意見回饋</a></li>
      <li><a href="#">檔案下載</a></li>
    </div>
    <b-container fluid id="mid_footer">
      <b-row>
        <b-col cols="12" md="3" lg="3">
          <!--<nuxt-link to="/"><img src="/footerlogo.svg"></nuxt-link>-->
          <nuxt-link to="/"><img src="~assets/footerlogo.svg"></nuxt-link>
          <p>甲種旅行社-交觀甲8340號 <br/>
          品保協會會員-品保北2498號</p>
        </b-col>
        <b-col cols="12" md="3" lg="3">
          <div class="align_center">
          <h5 style="color:#00A0E8">彭大家族旅行社有限公司</h5>
            <li><a href="https://line.me/R/ti/p/@pdtravel" target="_blank"><img src="~assets/line.svg" width="18px"> @pdtravel</a></li>
            <!--<li><a href="https://line.me/R/ti/p/@pdtravel" target="_blank"><img src="/line.svg" width="18px"> @pdtravel</a></li>-->
            <li><a href="mailto:service@pdtravel.com.tw" target="_blank"><b-icon icon="envelope-fill"></b-icon> service@pdtravel.com.tw</a></li>
            <li><a href="#" target="_blank"><b-icon icon="geo-alt"></b-icon> 新北市永和區智光街32巷3號</a></li>
            <li><a href="mailto:annie@pdtravel.com.tw" target="_blank"><b-icon icon="person-check-fill"></b-icon> 網站連絡人:陳詠菁 annie@pdtravel.com.tw</a></li>
          </div>
        </b-col>
        <b-col cols="12" md="3" lg="3">
          <!--<img src="/footer-banner.jpg">-->
          <img src="~assets/footer-banner.jpg">
        </b-col>
        <b-col cols="12" md="3" lg="3">
          <div><img src="~assets/footer-slogo01.png"><img src="~assets/footer-slogo02.png"></div>
          <div><img src="~assets/footer-slogo04.png"><img src="~assets/footer-slogo05.png"></div>
          
          <!--<div><img src="/footer-slogo01.png"><img src="/footer-slogo02.png"></div>
          <div><img src="/footer-slogo04.png"><img src="/footer-slogo05.png"></div>-->
        </b-col>
      </b-row>
    </b-container>
    <div class="copyright"> ©2020 PdTravel Copyright All rights reserved.</div>
</div>
</template>

<style scoped>

#footer {
  font-family: 'Noto Sans TC', sans-serif;
  font-weight: 300;
  background: #eaf4f9;
}
#bottom_link {
  width: 100%;
  text-align: center;
  background-color: #D1EDF3;
}
#bottom_link li{
display: inline-block;
list-style-type: none;
text-align: center;
padding:10px;
}
#bottom_link li:hover{
  background-color: #ebf5f7;
}
#bottom_link li a{
  text-decoration: none;
  color: #00A0E8;
}
.copyright{
    position: inherit;
    left: 0;
    width: 100%;
    background: #00A0E8;
    color: #CCD9E8;
    padding: 5px 15px;
    text-align: center;
}
#mid_footer{
  padding-top:30px;
  padding-bottom:30px;
  text-align: center;
}
#mid_footer p{
  font-size: 12px;
  line-height: 20px;
}
#mid_footer li{
  list-style-type: none;
}
#mid_footer li a{
  text-decoration: none;
}
.col{
  text-align: center;
}
@media screen and (max-width: 480px) {
  .align_center {
    text-align: center;
  }
}
@media screen and (min-width:1024px){
  .align_center {
    text-align: left;
  }
}
.col-md-3{
  padding: 10px 0;
}
</style>