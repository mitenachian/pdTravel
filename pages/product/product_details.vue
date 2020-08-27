<template>
  <div id="home_content">
      <div class="main_title">
          <h2> <b-icon icon="card-list"></b-icon>行程內容</h2>
      </div>
        <!--行程內容top card-->
        <b-card no-body class="overflow-hidden">
            <b-row no-gutters>
            <b-col md="4">
                <b-card-img src="https://picsum.photos/400/300?random=15" alt="Image" class="rounded-0"></b-card-img>
            </b-col>
            <b-col md="8">
                <b-card-body title="花東縱谷FUN鬆玩">
                <b-card-text>
                 <div class="detail_box1">
                    <div class="detail_item_div">
                        <span><b-icon icon="cursor-fill"></b-icon>出發: 2020 / 09 / 22 (二)</span>
                        <a href="#other_date"><span><b-icon icon="calendar2-check"></b-icon>其他出發日</span></a><br>
                        <span><b-icon icon="house"></b-icon>回程:</span> 2020 / 09 / 25 (四)<br>
                        <span><b-icon icon="calendar2-week-fill"></b-icon>天數:</span> 3
                    </div>
                    <div class="detail_item_div">
                        <span><b-icon icon="arrow-up-right-circle"></b-icon>交通:飛機(XX航空)</span>
                    </div>
                    <div class="detail_item_div">
                        <span><b-icon icon="person-plus"></b-icon>可報名人數:4</span><br>
                        <span><b-icon icon="person-check"></b-icon>最低報名人數:2</span>
                    </div>
                
                
                </div><!--detail_box-->
                 <div class="detail_box2">
                     <b-container fluid >
                        <b-row>
                            <b-col sm="12">
                                <div class="price_top"><p>售價<span>12,900</span>元起</p></div>
                            <b-row>
                                <div class="box2_item">
                                <b-col >6期2,150元起 <a href="#"><span><b-icon icon="info-circle"></b-icon>說明</span></a></b-col>
                                </div>
                            </b-row>
                            <b-row>
                                <b-col><b-button block variant="primary" @click="order()">訂購</b-button></b-col>
                            </b-row>
                            <b-row>
                                <div class="box2_item">
                                <b-col>分享到:
                                    <img src="@/assets/facebook.png"/>
                                    <img src="@/assets/instagram-sketched.png"/>
                                    <img src="@/assets/line.png"/>
                                    <img src="@/assets/twitter.png"/>
                                </b-col>
                                </div>
                            </b-row>
                            </b-col>
                        </b-row>
                        </b-container>
                </div><!--detail_box-->
                </b-card-text>
                </b-card-body>
            </b-col>

            </b-row>
        </b-card>
        <!--/行程內容top card-->
        <!--日曆區-->
        <div id="other_date">
            <b-container fluid>
                <b-row>
                    <b-col sm="12">
                        <h4>其它出發日</h4>
                    <b-row>
                        <b-col>
                            <no-ssr>
                            <v-calendar
                                class="custom-calendar"
                                :attributes="attributes"
                                :columns="screens({ default: 1, lg: 2 })"  is-expanded
                                >
                                    <div
                                    slot="day-content"
                                    slot-scope="{ day, attributes }"
                                    class="day_box overflow-hidden"
                                >
                                    <span>{{ day.day }}</span>
                                    <div class="flex-grow overflow-y-scroll overflow-x-auto" >
                                    <div
                                        style=""
                                        v-for="attr in attributes"
                                        class="text-xs"
                                        :class="attr.customData.class"
                                        :key="attr.key"
                                    >
                                    <b-link href="#"  variant="link">{{ attr.customData.title }}</b-link>
                                    </div>
                                    
                                    </div>
                                </div>
                            </v-calendar>
                            </no-ssr>
                        </b-col>
                    </b-row>
                    </b-col>
                </b-row>
            </b-container>
        </div>
        <!--/日曆區-->
        <!--Tab 區塊-->
        <div>
            <b-tabs content-class="mt-3" lazy>
                <b-tab title="優惠專案">
                    <b-alert show>
                        <p>
                        ★ 獨家直飛．雙點進出(仙台機場 x 花卷機場)，不走回頭路。<br/>
                        ★ 兩人同行+$99元贈高速WIFI上網吃到飽。<br/>
                        ★ 交通便利往來各大景點皆方便：北往青森奧入瀨溪流．秋田角館．岩手淨濱之土．弘前賞櫻；南向山形山寺．銀山溫泉．酒田山居倉庫．仙台松島。
                        </p>
                    </b-alert>
                </b-tab>
                <!--tab 分隔-->
                <b-tab title="交通資訊">
                    <b-alert show>
                        <p>
                        【飛機航班】<br/>
                        ★★★此行程搭配『台灣虎航 』，網頁公告之航班時間僅供參考，若有調整請依行程確認單及台灣虎航官網公告為準，恕不另行通知。★★★<br/>
                        ★★★低成本航空購買提醒(未免爭議請於購買前詳細閱讀，一經付款完成代表您了解並全權同意以下規範。)★★★<br/>
                        （1）本行程使用之機票為，團體經濟艙票種來回。 團體機票統一由航空公司劃位，無法自行選位，同行旅客座位有可能不相鄰，敬請見諒。<br/>
                        （2）注意事項及退票規定：機位一經確認後不可更改航班、日期與行程、不可退票、不可更改姓名或拼音，恕無法提供相關退費證明。<br/>
                        （3）取消規定：若因旅客因素取消行程，將收取全額機票費用及住宿飯店取消費用；若因天災等不可抗力之因素致班機延誤或取消，台灣虎航不提供旅客轉乘其他航空公司班機之服務、亦不提供安排旅客住宿之服務，且不負任何行程取消延誤責任，建議您另外加購相關保險。<br/>
                        （4）本行程含去程回程各20公斤托運行李及10公斤以內手提行李(可2件)。<br/>
                        （5）台灣虎航保有最終航班時間及託運行李之變更權利，如有異動請依照台灣虎航規定為準，恕不另行通知，恕無法另行退費，不便之處，敬請見諒。<br/>
                        （6）回程日計算未滿 2 歲需購買嬰兒票。因應航空公司飛安政策，每個航班僅提供10席嬰兒不佔位，如指定搭乘航班嬰兒人數超過規定限制、導致無法偕同嬰兒同行，可全額退費。一位成人僅能偕同一位不佔位嬰兒(恕不提供搖籃服務)；免費提供一件嬰兒推車託運，不提供座位/嬰兒搖籃/託運行李/機上餐食。<br/>

                        </p>
                    </b-alert>
                </b-tab>
                <!--tab 分隔-->
                <b-tab title="住宿飯店">
                    <b-alert show>
                        <p>
                        【飯店安排】<br/>
                        ◆入住日本飯店小提醒<br/>
                        （1）部分飯店提供之雙人入住床型為一中床(SEMI DBL)(床寬為120~140cm)， 比一般標準床略小，所使用的房型與單人房房型相同，若有小孩同行或求更好的住宿品質，建議選擇小孩佔床或加價改訂一大床或兩小床房型，報價請洽客服人員。<br/>
                        （2）飯店名稱所備註之房型為雙人入住床型，單人入住房型以入住當天飯店安排為準。<br/>
                        （3）滿6歲以上孩童皆須佔床，一間房恕無法接受2名(含)以上不佔床孩童入住。不佔床孩童無提供備品。<br/>
                        （4）如需更換飯店或調整入住天數，歡迎洽詢報價。<br/>

                        ◆盛岡飯店介紹：週二出發第4晚住宿，週三出發第1晚住宿。<br/>
                        ・盛岡站前Route-Inn飯店 Hotel Route-Inn Morioka Ekimae：JR盛岡站南出口步行約1分鐘。<br/>
                        ・盛岡城市飯店 Morioka City Hotel：JR盛岡站南口步行約2分鐘。<br/>
                        ・盛岡Unizo Inn Express Hotel：JR盛岡站西口步行約4分鐘。<br/>
                        </p>
                    </b-alert>
                </b-tab>

                <b-tab title="景點特色"><b-alert show>
                     <p>
                        【飯店安排】<br/>
                        ◆入住日本飯店小提醒<br/>
                        （1）部分飯店提供之雙人入住床型為一中床(SEMI DBL)(床寬為120~140cm)， 比一般標準床略小，所使用的房型與單人房房型相同，若有小孩同行或求更好的住宿品質，建議選擇小孩佔床或加價改訂一大床或兩小床房型，報價請洽客服人員。<br/>
                        （2）飯店名稱所備註之房型為雙人入住床型，單人入住房型以入住當天飯店安排為準。<br/>
                        （3）滿6歲以上孩童皆須佔床，一間房恕無法接受2名(含)以上不佔床孩童入住。不佔床孩童無提供備品。<br/>
                        （4）如需更換飯店或調整入住天數，歡迎洽詢報價。<br/>

                        ◆盛岡飯店介紹：週二出發第4晚住宿，週三出發第1晚住宿。<br/>
                        ・盛岡站前Route-Inn飯店 Hotel Route-Inn Morioka Ekimae：JR盛岡站南出口步行約1分鐘。<br/>
                        ・盛岡城市飯店 Morioka City Hotel：JR盛岡站南口步行約2分鐘。<br/>
                        ・盛岡Unizo Inn Express Hotel：JR盛岡站西口步行約4分鐘。<br/>
                        </p>
                </b-alert></b-tab>
                <b-tab title="特別提醒"><b-alert show>
                     <p>
                        【飯店安排】<br/>
                        ◆入住日本飯店小提醒<br/>
                        （1）部分飯店提供之雙人入住床型為一中床(SEMI DBL)(床寬為120~140cm)， 比一般標準床略小，所使用的房型與單人房房型相同，若有小孩同行或求更好的住宿品質，建議選擇小孩佔床或加價改訂一大床或兩小床房型，報價請洽客服人員。<br/>
                        （2）飯店名稱所備註之房型為雙人入住床型，單人入住房型以入住當天飯店安排為準。<br/>
                        （3）滿6歲以上孩童皆須佔床，一間房恕無法接受2名(含)以上不佔床孩童入住。不佔床孩童無提供備品。<br/>
                        （4）如需更換飯店或調整入住天數，歡迎洽詢報價。<br/>

                        ◆盛岡飯店介紹：週二出發第4晚住宿，週三出發第1晚住宿。<br/>
                        ・盛岡站前Route-Inn飯店 Hotel Route-Inn Morioka Ekimae：JR盛岡站南出口步行約1分鐘。<br/>
                        ・盛岡城市飯店 Morioka City Hotel：JR盛岡站南口步行約2分鐘。<br/>
                        ・盛岡Unizo Inn Express Hotel：JR盛岡站西口步行約4分鐘。<br/>
                        </p>
                    </b-alert></b-tab>
            </b-tabs>
        </div>
        <!--/tab區塊-->
        <hr>
        <!--交通資訊-->
        <div class="trans">
            <div class="sub_title">
                <h3><b-icon icon="shuffle"></b-icon>交通資訊</h3>
            </div>
            <div>
                <table class="tableclass" >
                <tr>
                    <td>第一天</td>
                    <td>華信航空-澎湖線 / 松山機場->澎湖機場</td>
                </tr>
                <tr>
                    <td>第三天</td>
                    <td>華信航空-澎湖線 / 澎湖機場->松山機場</td>
                </tr>
                </table><span>※實際航班依客服人員回覆為準</span>
            </div>
        </div>
        <!--/交通資訊-->
        <hr>
        <!--詳細行程-->
        <div class="project_deatil">
            <div class="sub_title">
                <h3><b-icon icon="card-checklist"></b-icon>詳細行程</h3>
            </div>
            <div>
                <div>
                    <div style="text-align:right;">
                    <b-button v-b-toggle.collapse-1.collapse-2.collapse-3 variant="primary" >收合所有行程</b-button>
                    </div>
                    <!--day-->
                    <b-collapse id="collapse-1" class="mt-2" visible>
                        <b-card>
                        <b-avatar size="4em" variant="primary">第1天</b-avatar>
                        <strong>第一天TITLE</strong>
                        <div class="left_border">
                            <p>
                                行程大剛之類的<br>
                                早餐：敬請自理<br>
                                午餐：環島之星觀光列車<br>
                                晚餐：飯店享用(花蓮美侖7~8月每週二入住自理+9/1起自理)<br>
                                花蓮壽豐遠雄悅來大飯店或參考其他住宿方案<br>
                            </p>
                        </div>
                        <b-button v-b-toggle.collapse-1-inner size="sm" variant="primary">更多詳細內容<b-icon icon="plus"></b-icon></b-button>
                        <b-collapse id="collapse-1-inner" class="mt-2">
                            <b-card>Hello!這裡放第一天詳細內容</b-card>
                        </b-collapse>
                        </b-card>
                    </b-collapse>
                    <!--day-->
                    <b-collapse id="collapse-2" class="mt-2" visible>
                        <b-card>
                        <b-avatar size="4em" variant="primary">第2天</b-avatar>
                        <strong>第二天TITLE</strong>
                        <div  class="left_border">
                            <p>
                                早餐：敬請自理<br>
                                午餐：環島之星觀光列車<br>
                                晚餐：飯店享用(花蓮美侖7~8月每週二入住自理+9/1起自理)<br>
                                花蓮壽豐遠雄悅來大飯店或參考其他住宿方案<br>
                            </p>
                        </div>
                        <b-button v-b-toggle.collapse-2-inner size="sm" variant="primary">更多詳細內容<b-icon icon="plus"></b-icon></b-button>
                        <b-collapse id="collapse-2-inner" class="mt-2">
                            <b-card>第二天詳細內容!</b-card>
                        </b-collapse>
                        </b-card>
                    </b-collapse>
                    <!--day-->
                    <b-collapse id="collapse-3" class="mt-2" visible>
                        <b-card>
                        <b-avatar size="4em" variant="primary">第3天</b-avatar>
                        <strong>第三天TITLE</strong>
                        <div  class="left_border">
                            <p>
                                早餐：敬請自理<br>
                                午餐：環島之星觀光列車<br>
                                晚餐：飯店享用(花蓮美侖7~8月每週二入住自理+9/1起自理)<br>
                                花蓮壽豐遠雄悅來大飯店或參考其他住宿方案<br>
                            </p>
                        </div>
                        <b-button v-b-toggle.collapse-3-inner size="sm" variant="primary">更多詳細內容<b-icon icon="plus"></b-icon></b-button>
                        <b-collapse id="collapse-3-inner" class="mt-2">
                            <b-card>第三天詳細內容</b-card>
                        </b-collapse>
                        </b-card>
                    </b-collapse>
                </div>
            </div>

        </div>
        <!--/詳細行程-->
         <hr>
        <!--住宿方案-->
        <div class="hotels">
            <div class="sub_title">
                <h3><b-icon icon="house-fill"></b-icon>住宿方案</h3>
            </div>
            <div>
                <table class="tableclass" >
                <tr>
                    <th colspan="2">飯店組合</th>
                    <th>房型/剩餘人數</th>
                    <th>成人價格</th>
                    <th>其它</th>
                </tr>
                <tr>
                    <td>組合1</td>
                    <td>花蓮壽豐遠雄悅來大飯店 (2晚)</td>
                    <td>四人房 / 餘2位</td>
                    <td>$10,999</td>
                    <td><b-icon icon="search"></b-icon>詳細價格</td>
                </tr>
                <tr>
                    <td>組合2</td>
                    <td>花蓮理想大地渡假飯店 </td>
                    <td>四人房 / 餘2位</td>
                    <td>$10,999</td>
                    <td><b-icon icon="search"></b-icon>詳細價格</td>
                </tr>
                <tr>
                    <td>組合3</td>
                    <td>花蓮理想大地渡假飯店 </td>
                    <td>二人房 / 餘2位</td>
                    <td>$10,999</td>
                    <td><b-icon icon="search"></b-icon>詳細價格</td>
                </tr>
                </table>
            </div>
        </div>
        <!--/住宿方案-->
         <hr>
        <!--作業說明-->
        <div>
            <div>
                <b-card title="作業說明" sub-title="敬請詳閱">
                    <b-card-text>
                   ►行程費用包含：
                    ＊高雄(斗六/嘉義/台南/新左營/屏東/枋寮)至花蓮『環島之星』觀光列車車票。
                    ＊花蓮至高雄(屏東) 南迴自強號車票。
                    (以上列車如遇指定班次客滿，將為旅客改訂提前或延後90分鐘內的班次)
                    ＊優質飯店住宿二晚及飯店早餐。
                    ＊行程表內所有交通、門票及餐食。
                    ＊行程旅遊專車導覽解說費及小費。
                    ＊保險： 一. 旅行業責任保險400萬意外險暨20萬意外醫療險。 
                    　　　　 二. 14歲以下及70歲以上旅客：旅行業責任保險200萬意外險暨20萬意外醫療險。 
                    ＊孩童不佔床(2歲以上未滿6歲)：含車票、行程間各點之接駁及保險；不含飯店床位、餐食及行程內之門票、餐食。因每間飯店的不佔床規定不同，請依各飯店規定為主，現場如有爭議或需要，請自行加付費用。
                    ＊嬰兒：費用僅含保險費與手續費，超過年齡或未報名者恕無法享用任何行程內之接送及餐食。
                    ►行程費用不包含：
                    ＊每日旅館客房清理及行李小費。
                    ＊表列上自理餐食費用支出。
                    ＊行程表上未表明之各項開支。
                    ＊純屬私人之消費：如飲料酒類、洗衣、電話及私人購物費。
                    </b-card-text>

                    <b-card-text>
                        <p>＊訂購本商品前請參閱相關規定及作業說明『各飯店房型及訂購注意事項』之規定。
                        ＊本商品為個人旅遊行程，請自行前往車站搭車，行程中景點將由司機導覽介紹（接駁部份不提供導覽介紹），故不另派領隊同行。
                        ＊行程為《合車制》，將依出發當日實際人數派遣車輛(小型、中型或大型旅遊車)。
                        ＊南迴自強號列車火車班次時有異動，請依旅遊券上標示之班次及時間為準。
                        ＊火車及高鐵座位皆為電腦系統劃位，恕無法保證其連續性，不便之處敬請見諒。
                        ＊住宿飯店之床型皆以易遊網服務人員回覆為主，如欲升等為非本行程所使用之房型，請依飯店規定補收差價。
                        ＊使用飯店公共水療設施時請記得攜帶泳裝及泳帽。
                        ＊防曬及禦寒用品請依個人需求攜帶。
                        ＊若遇天氣不佳或不可抗拒之因素，本公司保有取消或變更行程的權利。
                        ＊請於規定時間準時集合，行程如旅客因個人因素私自脫隊或集合不到，視同旅客放棄行程，本公司不予退費。
                        ＊請出發前確認參加人數，如當天臨時增加且未報名，因考慮車位調派及保險等問題，當地車行有權拒載，不便之處，敬請見諒。
                        ＊以上行程載明之車行時間僅供參考，因路況或假日遊客眾多行程順序將視情況前後更動。
                        ＊本行程部分搭乘巴士，請旅客自備暈車葯或其他隨身藥物。
                        </p>
                    </b-card-text>

                    <a href="#" class="card-link">link somthing</a>
                    <b-link href="#" class="card-link">Another link</b-link>
                </b-card>
            </div>
        </div>
        <!--/作業說明-->
        <hr>
        <!--訂購去-->
        <div>
            <b-button block variant="primary">訂購行程去</b-button>
            <hr>
        </div>


  </div>
</template>
<script>
  export default {
    data() {
      const month = new Date().getMonth();
      const year = new Date().getFullYear();
      return {
          /*日曆資料 */
attributes: [
        {
          key: 1,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 1),
        },
        {
          key: 2,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 2),
        },
        {
          key: 3,
          customData: {
            title: '$6,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 5),
        },
        {
          key: 4,
          customData: {
            title: '$9,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 6),
        },
        {
          key: 4,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 7),
        },
        {
          key: 5,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 11),
        },
        {
          key: 6,
          customData: {
            title: '$7,888起',
            class: 'text-black',
          },
          dates: { months: 5, ordinalWeekdays: { 2: 1 } },
        },
        {
          key: 7,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 22),
        },
        {
          key: 8,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 25),
        },
      ],
      }
    },
    methods: {
        screens(args) {
        if (process.client) {
            return this.$screens(args)
        } else {
            return 2 // <-- your default value
        }
        },
        order(){
            this.$router.push(
                { name: 'order'}
            );
        },
    },
        
  }
</script>
<style scoped>
#home_content{
    margin: auto 40px;
    font-family: 'Noto Sans TC', sans-serif;
}
.main_title{
    display: block;
    height: 80px;
    padding:10px;
    text-align: center;
    font-family: 'Noto Sans TC', sans-serif;
    color:#00A0E8;
}
.sub_title{
    display: block;
    color:#00A0E8;
}
.card{
    margin-bottom:20px;
}

.detail_box1 {
    float: left;
    height: 100%;
}
.detail_box2{
    float: left;
    height: 100%;
}
.detail_item_div{
    border-bottom: 1px dashed #89d7fc;
    margin-bottom: 10px;
}
.price_top{
    font-size:16px; 
    text-align:center;
}

.price_top span{
    font-size:24px;
    color:#00A0E8; 
    font-weight: 600;
}
.detail_box2 .box2_item{
    margin:30px auto;
}
@media screen and (max-width: 480px) {
  .detail_box1,.detail_box2 {
    width: 100%;
  }
}
@media screen and (min-width:1024px){
  .detail_box1 {
    width: 60%;
  }
  .detail_box2 {
    width: 40%;
  }
}
.tableclass {
    width: 100%;
    margin: 20px 20px 0 0;
}
table, th, td {
  border: 1px solid #89d7fc;
  border-collapse: collapse;
  padding:5px;
  color:slategray;
}

td:first-child{
    background-color:#89d7fc;
    text-align: center;
    color:#1b6a8f;
}


.left_border {
    border-left:#89d7fc dashed 1px;
    margin-left:30px;
    padding-left: 35px;
}
#other_date {
    height: 620px;
}
#other_date:target:before{
  display: block;
  content: "";
  height: 116px;
  margin: -116px 0 0;
}




</style>