<template>
  <section id="home_content">
    <b-container>
      <b-row class="pd_20">
        <b-col>
        <b-button variant="primary" squared disabled block> <b-icon icon="check-circle-fill"></b-icon>選擇商品 </b-button>
        </b-col>
        <b-col>
        <b-button variant="primary" squared disabled block><b-icon icon="check-circle-fill"></b-icon>填寫訂單</b-button>
        </b-col>
        <b-col>
        <b-button variant="primary" squared disabled block><b-icon icon="check-circle-fill"></b-icon>訂單付款</b-button>
        </b-col>
        <b-col>
        <b-button variant="primary" squared disabled block><b-icon icon="check-circle-fill"></b-icon>訂單完成</b-button>
        </b-col>
      </b-row>
    </b-container>
    <b-container>
      <!--付款方式-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">1</b-avatar> 訂單完成</h6>
            </template>
            <b-card-text>
            <div>
              資料內容待討論
              訂購詳情?
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>
<script>
  export default {
      data() {
      return {
     
      }
    },
    methods:{
   
    }
  }
</script>
<style scoped>

</style>