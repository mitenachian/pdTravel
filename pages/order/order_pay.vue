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
        <b-button variant="outline-secondary" squared disabled block>訂單完成</b-button>
        </b-col>
      </b-row>
    </b-container>
    <b-container>
      <!--付款方式-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">1</b-avatar> 付款方式</h6>
            </template>
            <b-card-text>
            <div>
              內容待討論
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
    <b-row class="text-center pd_20">
      <b-col>
         <b-alert v-model="showDismissibleAlert" variant="danger" dismissible>
                   <b-form-checkbox
                      id="checkbox-1"
                      v-model="is_pay"
                      value="Y"
                       unchecked-value="N"
                    >
                      尚未完成付款, 付款假設按鈕 打勾去完成訂單
                    </b-form-checkbox>
              </b-alert>
        <div>
          <b-button variant="secondary"  @click="done_order()">完成訂單</b-button>
        </div>
      </b-col>
    </b-row>    
  </section>
</template>
<script>
  export default {
      data() {
        return {
          is_pay:"N",
          showDismissibleAlert:false,
        }
    },
    methods:{
    done_order(){
      if(this.is_pay!='Y'){
        this.showDismissibleAlert=true;
      }else{
        //繼續購物流程
        this.$router.push(
                { 
                  name: 'order-order_complete' , 
                  params: {room_selected: this.room_selected,room_selected2:this.room_selected2 }
                }
            );
      }
    }
    }
  }
</script>
<style scoped>
.tableclass,.tableclass2 {
    width: 100%;
    margin: 20px 20px 0 0;
}
table, th,td {
  border-collapse: collapse;
  padding:5px;
  color:slategray;
  text-align: left;
}
td:first-child{
    color:#1b6a8f;
}
table.tableclass2{
  border-collapse: collapse;
  padding:5px;
  color:slategray;
}
table.tableclass2 td {
  text-align: left;
  border-top: 1px solid #1b6a8f;
}
.contract_area{
  height: 250px;
  overflow: scroll;
  border: 1px solid  #89d7fc;
}
</style>