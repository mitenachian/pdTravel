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
            <!--一個旅客資料-->
            <b-card-text>
              <div class="cus_data">
                <h6>旅客1-基本資料
                  <b-form-radio v-model="selected_main_contract" name="main_contract_radios" value="A">主要聯絡人</b-form-radio>
                </h6>
                    <b-form>
                      <b-row class="pd_bottom_10">
                        <b-col cols="12">
                              <b-row>
                                  <b-col cols="12" sm="3">
                                    <b-form-input id="last_name" required placeholder="姓" v-model='form.last_name'></b-form-input>
                                  </b-col>
                                  <b-col cols="12" sm="3">
                                    <b-form-input id="first_name" required placeholder="名字" v-model='form.first_name'></b-form-input>
                                  </b-col>
                                  <b-col cols="12" sm="2">
                                      <b-form-select v-model="form.sex_selected">
                                        <b-form-select-option :value="null">性別</b-form-select-option>
                                        <b-form-select-option value="male">男</b-form-select-option>
                                        <b-form-select-option value="Female">女</b-form-select-option>
                                      </b-form-select>
                                  </b-col>
                                  <b-col cols="12" sm="4">
                                    <b-form-input id="id_card" required placeholder="身分證字號"  v-model='form.id_card'></b-form-input>
                                  </b-col>
                              </b-row>
                        </b-col>
                      </b-row>
                      
                      <b-row class="pd_bottom_10">
                        <b-col cols="12" >
                              <b-row>
                                  <b-col cols="12" sm="5">
                                    <client-only>
                                      <v-date-picker
                                        v-model='form.birthday'
                                        :input-props='{
                                          placeholder: "出生日期",
                                        }'
                                        />
                                      </client-only>
                                  </b-col>
                                  <b-col cols="12" sm="3">
                                      <b-form-select required v-model="form.food_selected">
                                        <b-form-select-option :value="null">飲食限制</b-form-select-option>
                                        <b-form-select-option value="1">無</b-form-select-option>
                                        <b-form-select-option value="2">全素食</b-form-select-option>
                                        <b-form-select-option value="3">不吃豬肉</b-form-select-option>
                                        <b-form-select-option value="4">不吃牛肉</b-form-select-option>
                                      </b-form-select>
                                  </b-col>
                                  <b-col cols="12" sm="4">
                                    <b-form-input id="phone" required placeholder="連絡電話"></b-form-input>
                                  </b-col>
                              </b-row>
                        </b-col>
                      </b-row>
                      <b-row class="pd_bottom_10">
                        <b-col cols="12" >
                            <b-button v-b-toggle.collapse-1 variant="primary">其它自費加購行程</b-button>
                            <b-collapse id="collapse-1" class="mt-2">
                              <b-card>
                                <p class="card-text">
                                  <b-form-checkbox-group
                                    v-model="extral_pay_selected"
                                    :options="extral_pay_options"
                                    stacked
                                  ></b-form-checkbox-group>
                                </p>
                              </b-card>
                            </b-collapse>
                        </b-col>
                      </b-row>  
                    </b-form>
              </div>
            </b-card-text>
            <!--一個旅客資料結束-->
            <!--一個旅客資料-->
            <b-card-text>
              <div class="cus_data">
                <h6>旅客2-基本資料
                  <b-form-radio v-model="selected_main_contract" name="main_contract_radios" value="B">主要聯絡人</b-form-radio>
                </h6>
                    <b-form>
                      <b-row class="pd_bottom_10">
                        <b-col cols="12">
                              <b-row>
                                  <b-col cols="12" sm="3">
                                    <b-form-input id="last_name" required placeholder="姓" v-model='form.last_name'></b-form-input>
                                  </b-col>
                                  <b-col cols="12" sm="3">
                                    <b-form-input id="first_name" required placeholder="名字" v-model='form.first_name'></b-form-input>
                                  </b-col>
                                  <b-col cols="12" sm="2">
                                      <b-form-select v-model="form.sex_selected">
                                        <b-form-select-option :value="null">性別</b-form-select-option>
                                        <b-form-select-option value="male">男</b-form-select-option>
                                        <b-form-select-option value="Female">女</b-form-select-option>
                                      </b-form-select>
                                  </b-col>
                                  <b-col cols="12" sm="4">
                                    <b-form-input id="id_card" required placeholder="身分證字號"  v-model='form.id_card'></b-form-input>
                                  </b-col>
                              </b-row>
                        </b-col>
                      </b-row>
                      
                      <b-row class="pd_bottom_10">
                        <b-col cols="12" >
                              <b-row>
                                  <b-col cols="12" sm="5">
                                    <client-only>
                                      <v-date-picker
                                        v-model='form.birthday'
                                        :input-props='{
                                          placeholder: "出生日期",
                                        }'
                                        />
                                      </client-only>
                                  </b-col>
                                  <b-col cols="12" sm="3">
                                      <b-form-select required v-model="form.food_selected">
                                        <b-form-select-option :value="null">飲食限制</b-form-select-option>
                                        <b-form-select-option value="1">無</b-form-select-option>
                                        <b-form-select-option value="2">全素食</b-form-select-option>
                                        <b-form-select-option value="3">不吃豬肉</b-form-select-option>
                                        <b-form-select-option value="4">不吃牛肉</b-form-select-option>
                                      </b-form-select>
                                  </b-col>
                                  <b-col cols="12" sm="4">
                                    <b-form-input id="phone" required placeholder="連絡電話"></b-form-input>
                                  </b-col>
                              </b-row>
                        </b-col>
                      </b-row>
                      <b-row class="pd_bottom_10">
                        <b-col cols="12" >
                            <b-button v-b-toggle.collapse-1 variant="primary">其它自費加購行程</b-button>
                            <b-collapse id="collapse-1" class="mt-2">
                              <b-card>
                                <p class="card-text">
                                  <b-form-checkbox-group
                                    v-model="extral_pay_selected"
                                    :options="extral_pay_options"
                                    stacked
                                  ></b-form-checkbox-group>
                                </p>
                              </b-card>
                            </b-collapse>
                        </b-col>
                      </b-row>  
                    </b-form>
              </div>
            </b-card-text>
            <!--一個旅客資料結束-->
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
              <h6>主要聯絡人</h6>
               <b-form>
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="main_name" required placeholder="姓名"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="c_email" required placeholder="Email"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="c_phone" required placeholder="連絡電話"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="c_tel_1" required placeholder="市話,例:02-1234567"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
                    
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="3">
                                  <b-form-input id="c_postcode" required placeholder="郵遞區號"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="9">
                                  <b-form-input id="c_address" required placeholder="請填寫聯絡地址"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
                </b-form>
            </div>
            </b-card-text>
            <b-card-text>
            <div>
              <h6>緊急聯絡人</h6>
               <b-form>
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="5">
                                  <b-form-input id="mer_name" required placeholder="姓名"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="2">
                                  <b-form-input id="mer_q" required placeholder="關係"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="5">
                                  <b-form-input id="mer_phone" required placeholder="聯絡電話"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
                </b-form>
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
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                              <b-col cols="12" sm="2">
                                  門市取件
                                </b-col>
                                <b-col cols="12" sm="4">
                                  <b-form-select>
                                    <b-form-select-option  selected value="">選擇門市</b-form-select-option>
                                      <b-form-select-option value="a">Option A</b-form-select-option>
                                      <b-form-select-option value="b">Option B</b-form-select-option>
                                  </b-form-select>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
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
              <b-row class="pd_bottom_10">
                <b-col cols="12">
                  <b-row>
                    <b-form-group>
                      <b-form-radio v-model="selected_recipt" name="some-radios" value="A">
                        不需寄送代收轉付收據
                        <b-alert show>
                          本公司會依法開立『旅行業代收轉付收據』，若您訂購時勾選不用寄送者，
                          請親自至總公司索取，或來電(412-8001)或至我的訂單『與客服聯絡 』索取。
                        </b-alert>
                      </b-form-radio>
                      <b-form-radio v-model="selected_recipt" name="some-radios" value="B">
                        寄送代收轉付收據
                      </b-form-radio>
                    </b-form-group>
                  </b-row>
                  <div v-if="selected_recipt=='B'">
                  <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="company_name" required placeholder="公司名稱"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="6">
                                  <b-form-input id="company_id" required placeholder="統一編號"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>                   
                  </b-row>
                    <b-row class="pd_bottom_10">
                      <b-col cols="12">
                            <b-row>
                                <b-col cols="12" sm="3">
                                  <b-form-input id="company_postcode" required placeholder="郵遞區號"></b-form-input>
                                </b-col>
                                <b-col cols="12" sm="9">
                                  <b-form-input id="company_address" required placeholder="請填寫地址"></b-form-input>
                                </b-col>
                            </b-row>
                      </b-col>
                    </b-row>
                  </div>
                </b-col>
              </b-row>
             </div>
            </b-card-text>
          </b-card>
          <!--4收據資料-->
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">5</b-avatar> 
              其它備註</h6>
            </template>
            <b-card-text>
            <div>
              <b-form-textarea
                id="custom_note"
                v-model="form.custom_note"
                placeholder="請輸入其它備註事項"
                rows="3"
                max-rows="6"
              ></b-form-textarea>
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
              <b-button variant="link"  @click="modalShow = !modalShow"><b-icon icon="eye"></b-icon>檢視明細</b-button>
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
            <b-button variant="secondary"  @click="pay_order()">送出訂單資料</b-button>
          </div>
        </b-col>
      </b-row>
      <!--modal-->
      <b-modal v-model="modalShow" title="訂單詳情">
        <p>一些資料</p>
      </b-modal>
  </section>
</template>
<script>
  export default {
      data() {
      return {
        modalShow: false,
        form: {
          sex_selected:null,
          birthday: '',
          first_name: '',
          last_name: '',
          id_card: '',
          food_selected:null,
          custom_note:'',
        },
        selected_main_contract:null,
        extral_pay_selected: [], // Must be an array reference!
        extral_pay_options: [
          { text: '行程A', value: '2000' },
          { text: '行程B', value: '3000' },
          { text: '行程C', value: '4000' },
          { text: '行程D', value: '5000' }
        ],
        selected_recipt:'A',
      }
    },
    methods:{
          pay_order(){
              //繼續購物流程
              this.$router.push( { 
                        name: 'order-order_pay' , 
                        params: {foo: 1 }
                      });
          }
    }
  }
</script>
<style scoped>

</style>