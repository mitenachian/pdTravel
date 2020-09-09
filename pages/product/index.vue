<template>
  <section id="home_content">
      <div class="main_title">
          <h2> <b-icon icon="geo-alt"></b-icon>精選行程列表</h2>
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

</style>