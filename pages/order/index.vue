<template>
  <div id="order_content">
    <div>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" >訂單明細</h6>
            </template>
            <b-card-text>商品名稱:OOXX自由行</b-card-text>
            <b-card-text>出發日期:2020/08/27
            </b-card-text>
          </b-card>
    </div>


  </div>
</template>
<script>
  export default {
    data() {
      return {
      }
    },
  }
</script>
<style scoped>
#order_content{
    margin: 20px 40px;
    font-family: 'Noto Sans TC', sans-serif;
}

</style>