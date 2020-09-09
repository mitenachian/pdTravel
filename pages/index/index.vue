<template>
  <section id="home_content">
      <b-container fluid>
      <div class="main_title">
          <h2> <b-icon icon="geo-alt"></b-icon>主打行程</h2>
      </div>
      <!--行程card分隔線-->
        <b-card no-body class="overflow-hidden prd_item" v-for="item in prd_list" :key="item.prd_id">
            <b-row no-gutters>
            <b-col md="4">
                <b-card-img :src="item.prd_img" alt="Image" class="rounded-0"></b-card-img>
            </b-col>
            <b-col md="8">
                <b-card-body :title="item.prd_title">
                <b-card-text>
                 <div>
                     <div v-html="item.prd_content"></div>
                <div class="clearfix"></div>
                    <div>
                        <b-button block variant="primary"  @click="linkTo()">{{ item.prd_price }}起</b-button>
                    </div>
                </div>
                </b-card-text>
                </b-card-body>
            </b-col>
            </b-row>
        </b-card>
        <!--行程card分隔線-->
        <hr>
        <div class="main_title">
          <h2> <b-icon icon="camera-reels-fill"></b-icon>精選影片</h2>
      </div>
  <div>
     <b-row>
         <b-col md="4">
            <b-card border-variant="light" header="【彭大家族】沖繩好好玩系列_觀光篇-NO.001" class="text-center">
                <b-card-text>
                <iframe src="https://www.youtube.com/embed/H_1vQB1VviU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </b-card-text>
            </b-card>
         </b-col>
         <b-col md="4">
            <b-card border-variant="light" header="【彭大家族】沖繩好好玩系列_觀光篇-NO.001" class="text-center">
                <b-card-text>
                <iframe src="https://www.youtube.com/embed/H_1vQB1VviU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </b-card-text>
            </b-card>
         </b-col>
         <b-col md="4">
            <b-card border-variant="light" header="【彭大家族】沖繩好好玩系列_觀光篇-NO.001" class="text-center">
                <b-card-text>
                <iframe src="https://www.youtube.com/embed/H_1vQB1VviU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </b-card-text>
            </b-card>
         </b-col>
    </b-row>
  </div>
      </b-container>
  </section>
</template>
<script>
import prd_data from 'static/data/demo_prdData.json'
export default {
 data() {
      return {
        prd_list:prd_data,
      }
 },
methods:{
    linkTo(){
        this.$router.push(
            { name: 'product-product_details'}
        );
    }
}
}
</script>
<style scoped>
#home_content{
    margin: auto 40px;
}
.main_title{
    display: block;
    height: 80px;
    padding:10px;
    text-align: center;
    font-family: 'Noto Sans TC', sans-serif;
    color:#00A0E8;
}
.card{
    margin-bottom:20px;
}
.prd_item:hover {
     box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
     opacity: 0.8;
}
.videoBox{
    padding: 10px;
    border:#00A0E8 1px solid;
    border-radius: 5px;
}
</style>