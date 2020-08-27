<template>
<b-container  fluid="lg" class="w100">
    <div id="searchTerm" class="box_shadow">
        <b-row>
          <b-col sm="2">
            <label><b-icon icon="cursor"></b-icon> 旅遊區域</label>
            <b-form-select v-model="area_selected" :options="area_options"></b-form-select>
          </b-col>
          <b-col sm="2">
            <label><b-icon icon="signpost2-fill"></b-icon> 目的地</label>
            <b-form-select v-model="dis_selected" :options="dis_options"></b-form-select>
          </b-col>
          <b-col sm="3">
            <label> <b-icon icon="calendar2-check"></b-icon> 出發時間</label>
            <client-only>
                  <v-date-picker
                  mode='range'
                  v-model='search_date_range'
                  :input-props='{
                    placeholder: "選擇時間",
                  }'
                  />
            </client-only>
          </b-col>
          <b-col sm="3">
            <label><b-icon icon="search"></b-icon> 關鍵字</label>
            <b-form-input v-model="search_text" placeholder="輸入關鍵字"></b-form-input>
          </b-col>
          <b-col sm="2">
           <b-button block variant="primary"  style="margin-top:30px;">送出搜尋</b-button>
          </b-col>
        </b-row>
    </div>
</b-container>
</template>
<script>
  export default {
    data() {
      return {
        search_date_range: {
          start: '', // Jan 16th, 2018 new Date(2018, 0, 16)
          end: '',// Jan 19th, 2018 new Date(2018, 0, 16)
        },
        search_text: null,
        area_selected: null,
        area_options: [
          { value: null, text: '選擇旅遊區域' },
          { value: 'a', text: '東北亞' },
          { value: 'b', text: '東南亞' },
          { value: { C: '3PO' }, text: '澳洲' },
          { value: 'd', text: '大洋洲', disabled: true }
        ],
        dis_selected: null,
        dis_options: [
          { value: null, text: '選擇旅遊目地' },
          { value: 'a', text: '不限' },
          { value: 'b', text: '不限' },
          { value: { C: '3PO' }, text: '不限' },
        ]
      }
    }
  }
</script>
<style scoped>
#searchTerm {
font-family: 'Noto Sans TC', sans-serif;
margin: 40px auto;
padding: 10px 30px;
background: #EAF4F9;
width: 100%;
min-height: 120px;
border-radius: 10px;
}
.w100{
  max-width: 100%;
}

</style>