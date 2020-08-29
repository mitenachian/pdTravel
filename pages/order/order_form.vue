<template>
  <section id="home_content">
    <b-container fluid="md">
      <b-row class="pd_20">
        <b-col>
        <b-button variant="primary" squared disabled block> <b-icon icon="check-circle-fill"></b-icon>選擇商品 </b-button>
        </b-col>
        <b-col>
        <b-button variant="primary" squared disabled block> <b-icon icon="check-circle-fill"></b-icon>填寫訂單</b-button>
        </b-col>
        <b-col>
        <b-button variant="outline-secondary" squared disabled block>訂單付款</b-button>
        </b-col>
        <b-col>
        <b-button variant="outline-secondary" squared disabled block>訂單完成</b-button>
        </b-col>
      </b-row>
    </b-container>
    <b-container fluid="md">
      <!--訂購資料填寫-->
      <b-row>
        <b-col sm="8">
          <!--1填寫旅客資訊-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">1</b-avatar> 
              填寫旅客資訊</h6>  
              <b-badge pill variant="danger">*為必填如欲修改會員資料，請至「會員中心」修改</b-badge>
            </template>
            <b-card-text>
            <div>
                  <b-form >
                    <b-form-group
                      id="input-group-1"
                      label="輸入性名:"
                      label-for="input-1"
                      description="We'll never share your email with anyone else."
                    >
                      <b-form-input
                        id="input-1"
                        v-model="form.email"
                        type="email"
                        required
                        placeholder="Enter email"
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
                      <b-form-input
                        id="input-2"
                        v-model="form.name"
                        required
                        placeholder="Enter name"
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group id="input-group-3" label="Food:" label-for="input-3">
                      <b-form-select
                        id="input-3"
                        v-model="form.food"
                        :options="foods"
                        required
                      ></b-form-select>
                    </b-form-group>

                    <b-form-group id="input-group-4">
                      <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
                        <b-form-checkbox value="me">Check me out</b-form-checkbox>
                        <b-form-checkbox value="that">Check that out</b-form-checkbox>
                      </b-form-checkbox-group>
                    </b-form-group>
                  </b-form>
            </div>
            </b-card-text>
          </b-card>
          <!--2訂單聯絡人-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">2</b-avatar> 
              訂單聯絡人</h6>  
              <b-badge pill variant="danger">*為必填行程前確認相關事宜對象</b-badge>
            </template>
            <b-card-text>
            <div>
                ....
            </div>
            </b-card-text>
          </b-card>
          <!--3取件方式-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">3</b-avatar> 
              取件方式</h6>
            </template>
            <b-card-text>
            <div>
              一些資料
            </div>
            </b-card-text>
          </b-card>
          <!--4收據資料-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">4</b-avatar> 
              收據資料</h6>
            </template>
            <b-card-text>
            <div>
              一些資料
            </div>
            </b-card-text>
          </b-card>
          <!--4收據資料-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">5</b-avatar> 
              服務區域</h6>
            </template>
            <b-card-text>
            <div>
              一些資料
            </div>
            </b-card-text>
          </b-card>
        </b-col>
        <!--右邊資料-->
        <b-col sm="4">
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" >訂購明細</h6>
            </template>
            <b-card-text>
            <div>
              商品售價31,000 元
              <b-button variant="link"><b-icon icon="eye"></b-icon>檢視明細</b-button>
            </div>
            </b-card-text>
            <template v-slot:footer>
              <em>應付總額: $31,000元</em>
            </template>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
      <b-row class="text-center pd_20">
        <b-col>
          <div>
            <b-button variant="secondary">送出訂單資料</b-button>
          </div>
        </b-col>
      </b-row>
  </section>
</template>
<script>
  export default {
      data() {
      return {
        form: {
          email: '',
          name: '',
          food: null,
          checked: []
        },
        foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
        show: true
      }
    },
    methods:{

    }
  }
</script>
<style scoped>

</style>