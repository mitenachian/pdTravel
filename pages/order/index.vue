<template>
  <section id="home_content">
    <b-container>
      <b-row class="pd_20">
        <b-col>
        <b-button variant="primary" squared disabled block> <b-icon icon="check-circle-fill"></b-icon>選擇商品 </b-button>
        </b-col>
        <b-col>
        <b-button variant="outline-secondary" squared disabled block>填寫訂單</b-button>
        </b-col>
        <b-col>
        <b-button variant="outline-secondary" squared disabled block>訂單付款</b-button>
        </b-col>
        <b-col>
        <b-button variant="outline-secondary" squared disabled block>訂單完成</b-button>
        </b-col>
      </b-row>
    </b-container>
    <b-container>
      <!--訂單明細1-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">1</b-avatar> 訂單明細</h6>
            </template>
            <b-card-text>
            <div>
                <table class="tableclass" >
                <tr>
                    <td>商品名稱</td>
                    <td>
                      花蓮．太魯閣/海洋公園/賞鯨/兆豐農場 輕鬆選 3天(桃竹可出發)
                    </td>
                </tr>
                <tr>
                    <td>出發日期</td>
                    
                    <td>2020 年 08 月 31 日 (一)</td>
                </tr>
                </table>
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
      <!--選擇交通-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">2</b-avatar> 選擇交通</h6>
            </template>
            <b-card-text>
            <div>
                <table class="tableclass2" >
                <tr>
                    <th>行程</th>
                    <th>訂位</th>
                    <th>選擇交通</th>
                    <th>班次</th>
                    <th>出發地</th>
                    <th>目的地</th>
                    <th>出發時間</th>
                    <th>抵達時間</th>
                    <th>成人差價</th>
                    <th>資深公民差價</th>
                    <th>兒童差價</th>
                    
                </tr>
                <tr>
                    <td>第1天</td>
                    <td><b-form-radio name="radio-day1-trans" size="sm"></b-form-radio></td>
                    <td>華信航空-澎湖縣</td>
                    <td>--</td>
                    <td>松山機場</td>
                    <td>澎湖機場</td>
                    <td>--</td>
                    <td>--</td>
                    <td>0元</td>
                    <td>0元</td>
                    <td>0元</td>
                </tr>
                <tr>
                    <td>第3天</td>
                    <td><b-form-radio name="radio-day3-trans" size="sm" ></b-form-radio></td>
                    <td>華信航空-澎湖縣</td>
                    <td>--</td>
                    <td>澎湖機場</td>
                    <td>松山機場</td>
                    <td>--</td>
                    <td>--</td>
                    <td>0元</td>
                    <td>0元</td>
                    <td>0元</td>
                </tr>
                </table>
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
      <!--選擇房型&人數-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">3</b-avatar> 選擇房型與人數</h6>
            </template>
            <b-card-text>
            <div>
                <table class="tableclass2" >
                <tr>
                    <th>商品</th>
                    <th>價格</th>
                    <th>訂購間數</th>
                    
                </tr>
                <tr>
                    
                    <td>
                      <b-form-radio name="radio-roombook" size="sm">
                      	組合1	捷絲旅花蓮中正館 (2晚)</b-form-radio>
                    </td>
                    <td>四人房-8,990元</td>
                    <td>
                      <b-form-select v-model="room_selected" :options="room_options" class="mb-1">
                      </b-form-select>
                    </td>
                </tr>
                <tr>
                    <td>
                      <b-form-radio name="radio-roombook" size="sm">
                      		組合2 花蓮翰品酒店 (2晚)</b-form-radio>
                    </td>
                    <td>雙人房-8,990元</td>
                    <td>
                      <b-form-select v-model="room_selected2" :options="room_options2" class="mb-1">
                      </b-form-select>
                    </td>
                </tr>
                </table>
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
      <!--選擇房型&人數-->
      <b-row>
        <b-col>
          <b-card header-tag="header">
            <template v-slot:header>
              <h6 class="mb-0" ><b-avatar size="sm" variant="primary">4</b-avatar>旅遊契約書</h6>
            </template>
            <b-card-text>
            <div class="contract_area"  ref="pdfDom">
              <div bgcolor="#FFFFFF" text="#000000" leftmargin="0" topmargin="0" marginwidth="0" marginheight="0">
                <table width="90%" border="0" cellspacing="0" cellpadding="5" align="center">
                  <tbody><tr height="100">
                    <td align="left">
                      <p align="center">
                        <font size="3"><b>國內旅遊定型化契約</b></font>
                        <span style="margin-left:30px;"><a href="#" @click="printDomVal"><u>友善列印</u></a></span>
                      </p>
                      <br>
                      <div align="right"> </div>

                      中華民國105年12月12日觀業字第1050922838號函修正 <br><br>

                      <table border="0" width="100%">
                        <tbody><tr height="30">
                          <td align="left">立契約書人</td>
                          <td align="right"> (<font color="blue">本契約本契約審閱期間至少一日，　 　 年　 　 月　 　 日由甲方攜回審閱)</font>
                          </td>
                        </tr>
                        <tr height="30">
                          <td align="left">
                            <font color="blue">旅&nbsp; &nbsp; &nbsp; &nbsp; 客(以下稱甲方)：(第一位旅客姓名)等&nbsp;
                              
                                
                                  <span style="margin-left:20px"></span>
                                
                              
                              &nbsp;人
                          </font></td>
                          <td align="right"></td>
                        </tr>
                        <tr height="30">
                          <td align="left">
                            <font color="blue">
                              緊急聯絡人姓名：__________
                              &nbsp; &nbsp; &nbsp; &nbsp;與旅客關係：__________
                              &nbsp; &nbsp; &nbsp; &nbsp;電話：__________
                            </font>
                          </td>
                          <td align="right"></td>
                        </tr>
                        <tr height="30">
                          <td align="left">
                            <font color="blue">旅行業(以下稱乙方)：易遊網旅行社股份有限公司</font>
                          </td>
                          <td align="right"></td>
                        </tr>
                        <tr height="30">
                          <td align="left">甲乙雙方同意就本旅遊事項，依下列約定辦理。</td>
                          <td align="right"></td>
                        </tr>
                      </tbody></table>

                      <p>
                        <b>第一條（國內旅遊之意義）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 本契約所謂國內旅遊，指在臺灣、澎湖、金門、馬祖及其他自由地區之我國疆域範圍內之旅遊。
                      </p>
                      <p>
                        <b>第二條（適用之範圍）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲乙雙方關於本旅遊之權利義務，依本契約條款之約定定之；本契約中未約定者，適用中華民國有關法令之規定。
                      </p>
                      <p>
                        <b>第三條（旅遊團名稱、旅遊行程及廣告責任）</b><br>
                        <font color="blue">&nbsp; &nbsp; &nbsp; &nbsp; 本旅遊團名稱為 花蓮．太魯閣/海洋公園/賞鯨/兆豐農場 輕鬆選 3天(桃竹可出發)</font><br>
                        <font color="blue">&nbsp; &nbsp; &nbsp; &nbsp; 一、 旅遊地區（國家、城市或觀光地點）：台灣 - 花蓮</font><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 二、 行程（啟程出發地點、回程之終止地點、日期、交通工具、住宿旅館、餐飲、遊覽、安排購物行程及其所附隨之服務說明）：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        與本契約有關之附件、廣告、宣傳文件、行程表或說明會之說明內容均視為本契約內容之一部分。乙方應確保廣告內容之真實，對甲方所負之義務不得低於廣告之內容。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 第一項記載得以所刊登之廣告、宣傳文件、行程表或說明會之說明內容代之。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        未記載第一項內容或記載之內容與刊登廣告、宣傳文件、行程表或說明會之說明記載不符者，以最有利於旅客之內容為準。<br>
                      </p>
                      <p>
                        <b>第四條（集合及出發時地）</b><br>
                        <font color="blue">&nbsp; &nbsp; &nbsp; &nbsp; 甲方應於 
                          民國 109 年 08 月 31 日 (依行程確認單的時間)準時集合出發。</font>
                        甲方未準時到約定地點集合致未能出發，亦未能中途加入旅遊者，視為甲方任意解除契約，乙方得依第十二條之約定，行使損害賠償請求權。
                      </p>
                      <p>
                        <b>第五條（旅遊費用及其付款方式）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 除雙方有特別約定者外，甲方應依下列約定繳付：<br>
                        <font color="blue">&nbsp; &nbsp; &nbsp; &nbsp; 一、 本次旅遊總費用為<u>__________</u>元；簽訂本契約時，甲方應繳付新臺幣<u>__________</u>元。</font><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 二、 其餘款項於出發前三日或說明會時繳清。 <br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 前項之特別約定，除經雙方同意並記載於本契約第三十二條，雙方不得以任何名義要求增減旅遊費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 前項之特別約定，除經雙方同意並記載於本契約第三十二條，雙方不得以任何名義要求增減旅遊費用。
                      </p>
                      <p>
                        <b>第六條 (旅客怠於給付旅遊費用之效力)</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        因可歸責於甲方之事由，怠於給付旅遊費用者，乙方得定相當期限催告甲方給付，甲方逾期不為給付者，乙方得終止契約。甲方應賠償之費用，依第十二條約定辦理；乙方如有其他損害，並得請求賠償。
                      </p>
                      <p>
                        <b>第七條 (旅客協力義務)</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 旅遊需甲方之行為始能完成，而甲方不為其行為者，乙方得定相當期限，催告甲方為之。甲方逾期不為其行為者，乙方得終止契約，並得請求賠償因契約終止而生之損害。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 旅遊開始後，乙方依前項規定終止契約時，甲方得請求乙方墊付費用將其送回原出發地。於到達後，由甲方附加年利率5%利息償還乙方。 <br>
                      </p>
                      <p>
                        <b>第八條（旅遊費用所涵蓋之項目）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方依第五條約定繳納之旅遊費用，除雙方依第三十二條另有約定外，應包括下列項目：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 一、 代辦證件之行政規費：乙方代理甲方辦理所須證件之規費。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 二、 交通運輸費：旅程所需各種交通運輸之費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 三、 餐飲費：旅程中所列應由乙方安排之餐飲費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 四、 住宿費：旅程中所需之住宿旅館之費用，如甲方需要單人房，經乙方同意安排者，甲方應補繳所需差額。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 五、 遊覽費用：旅程中所列之一切遊覽費用及入場門票費等。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 六、 接送費：旅遊期間機場、港口、車站等與旅館間之一切接送費用。 <br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 七、 行李費：團體行李往返機場、港口、車站等與旅館間之一切接送費用及團體行李接送人員之小費，行李數量之重量依航空公司規定辦理。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 八、 稅捐：機場服務稅捐及團體餐宿稅捐等。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 九、 服務費：隨團服務人員之報酬及其他乙方為甲方安排服務人員之報酬。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 十、 保險費：責任保險及履約保證保險。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        前項第二款交通運輸費及第五款遊覽費用，其費用於契約簽訂後經政府機關或經營管理業者公布調高或調低時，應由甲方補足，或由乙方退還。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        第一項第二款至第五款之年長者門票減免、兒童住宿不佔床及各項優惠等，詳如附件（報價單）。如契約相關文件均未記載者，甲方得請求如實退還差額。<br>
                      </p>
                      <p>
                        <b>第九條（旅遊費用所未涵蓋項目）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 除雙方依第三十二條另有約定外，第五條之旅遊費用，不包括下列項目：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 一、 非本旅遊契約所列行程之一切費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 二、 甲方個人費用：如自費行程費用、行李超重費、飲料及酒類、洗衣、電話、網際網路使用費、私人交通費、行程外陪同購物之報酬、自由活動費、個人傷病醫療費、宜自行給與提供個人服務者（如旅館客房服務人員）之小費或尋回遺失物費用及報酬。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 三、 未列入旅程之機票及其他有關費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 四、 建議給予司機或隨團服務人員之小費。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 五、 保險費：甲方自行投保旅行平安險之費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 六、 其他由乙方代辦代收之費用。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項第二款、第四款建議給予之小費，乙方應於出發前，說明各觀光地區小費收取狀況及約略金額。<br>
                      </p>
                      <p>
                        <b>第十條（組團旅遊最低人數）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; <font color="blue">本旅遊團須有&nbsp;1 人以上簽約參加始組成</font>。如未達前定人數，乙方應於預訂出發之七日前通知甲方解除契約，怠於通知致甲方受損害者，乙方應賠償甲方損害。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項組團人數如未記載者，視為無最低組團人數；其保證出團者，亦同。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 乙方依第一項規定解除契約後，得依下列方式之一，返還或移作依第二款成立之新旅遊契約之旅遊費用：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 一、 退還甲方已交付之全部費用。但乙方已代繳之行政規費得予扣除。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 二、 徵得甲方同意，訂定另一旅遊契約，將依第一項解除契約應返還甲方之全部費用，移作該另訂之旅遊契約之費用全部或一部。如有超出之賸餘費用，應退還甲方。 <br>
                      </p>
                      <p>
                        <b>第十一條（因可歸責於旅行業之事由致無法成行）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        因可歸責於乙方之事由，致旅遊活動無法成行者，乙方於知悉旅遊活動無法成行時，應即通知甲方且說明其事由，並退還甲方已繳之旅遊費用。前項情形，乙方怠於通知者，應賠償甲方依旅遊費用之全部計算之違約金。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方已為第一項通知者，則按通知到達甲方時，距出發日期時間之長短，依下列規定計算其應賠償甲方之違約金：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 一、 通知於出發日前第四十一日以前到達者，賠償旅遊費用百分之五。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 二、 通知於出發日前第三十一日至第四十日以內到達者，賠償旅遊費用百分之十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 三、 通知於出發日前第二十一日至第三十日以內到達者，賠償旅遊費用百分之二十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 四、 通知於出發日前第二日至第二十日以內到達者，賠償旅遊費用百分之三十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 五、 通知於出發日前一日到達者，賠償旅遊費用百分之五十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 六、 通知於出發當日以後到達者，賠償旅遊費用百分之一百。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 甲方如能證明其所損害超過前項各款基準者，得就其實際損害請求賠償。<br>
                      </p>
                      <p>
                        <b>第十二條<font color="blue">（出發前旅客任意解除契約及其責任）</font></b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方於旅遊活動開始前得解除契約。但應於乙方提供收據後，繳交行政規費，並依列基準賠償：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 一、 旅遊開始前第四十一日以前解除契約者，賠償旅遊費用百分之五。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 二、 旅遊開始前第三十一日至第四十日以內解除契約者，賠償旅遊費用百分之十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 三、 旅遊開始前第二十一日至第三十日以內解除契約者，賠償旅遊費用百分之二十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 四、 旅遊開始前第二日至第二十日以內解除契約者，賠償旅遊費用百分之三十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 五、 旅遊開始前一日解除契約者，賠償旅遊費用百分之五十。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 六、 旅遊開始日或開始後解除契約或未通知不參加者，賠償旅遊費用百分之一百。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 前項規定作為損害賠償計算基準之旅遊費用，應先扣除行政規費後計算之。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 乙方如能證明其所受損害超過第一項之基準者，得就其實際損害請求賠償。<br>
                      </p>
                      <p>
                        <b>第十三條（出發前有法定原因解除契約）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 因不可抗力或不可歸責於雙方當事人之事由，致本契約之全部或一部無法履行時，任何一方得解除契約，且不負損害賠償責任。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項情形，乙方應提出已代繳之行政規費或履行本契約已支付之全部必要費用之單據，經核實後予以扣除，並將餘款退還甲方。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 任何一方知悉旅遊活動無法成行時，應即通知他方並說明其事由；其怠於通知致他方受有損害時，應負賠償責任。 <br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 為維護本契約旅遊團體之安全與利益，乙方依第一項為解除契約後，應為有利於旅遊團體之必要措置。<br>
                      </p>
                      <p>
                        <b>第十四條（出發前有客觀風險事由解除契約）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        出發前，本旅遊團所前往旅遊地區之一，有事實足認危害旅客生命、身體、健康、財產安全之虞者，準用前條之規定，得解除契約。但解除之一方，應按旅遊費用百分之五補償他方（不得超過百分之五）。
                      </p>
                      <p>
                        <b>第十五條（證照之保管及返還）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方代理甲方處理旅遊所需之手續，應妥慎保管甲方之各項證件；如有遺失或毀損，應即主動補辦。如致甲方受損害時，應賠償甲方之損害。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項證件，乙方及其受僱人應以善良管理人之注意保管之；甲方得隨時取回，乙方及其受僱人不得拒絕。<br>
                      </p>
                      <p>
                        <b>第十六條（旅客之變更權）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方於旅遊開始_____日前，因故不能參加旅遊者，得變更由第三人參加旅遊。乙方非有正當理由者，不得拒絕。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        前項情形，如因而增加費用，乙方得請求該變更後之第三人給付；如減少費用，甲方不得請求返還。甲方並應於接到乙方通知後_____日內協同該第三人到乙方營業處所辦理契約承擔手續。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 承受本契約之第三人，與甲乙雙方辦理承擔手續完畢起，承繼甲方基於本契約一切權利義務。<br>
                      </p>
                      <p>
                        <b>第十七條（旅行業務之轉讓）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        乙方於出發前如將本契約變更轉讓予其他旅行業者，應經甲方書面同意。甲方如不同意者，得解除契約，乙方應即時將甲方已繳之全部旅遊費用退還；甲方受有損害者，並得請求賠償。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        甲方於出發後始發覺或被告知本契約已轉讓其他旅行業，乙方應賠償甲方全部旅遊費用百分之五之違約金；甲方受有損害者，並得請求賠償。受讓之旅行業或其履行輔助人，關於旅遊義務之履行，有故意或過失時，甲方亦得請求讓與之旅行業者負責。<br>
                      </p>
                      <p>
                        <b>第十八條（旅程內容之實現及例外）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        旅程中之食宿、交通、旅程、觀光點及遊覽項目等，應依本契約所訂等級與內容辦理，甲方不得要求變更，但乙方同意甲方之要求而變更者，不在此限，惟其所增加之費用應由甲方負擔。除非有本契約第十三條或第二十一條之情事，乙方不得以任何名義或理由變更旅遊內容。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 因可歸責於乙方之事由，致未達本契約所定旅程、交通、食宿或遊覽項目等事宜時，甲方得請求乙方賠償各該差額二倍之違約金。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方應提出前項差額計算之說明，如未提出差額計算之說明時，其違約金之計算至少為全部旅遊費用之百分之五。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方受有損害者，另得請求損害賠償。<br>
                      </p>
                      <p>
                        <b>第十九條（因可歸責於旅行業之事由致行程延誤）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 因可歸責於乙方之事由，致延誤行程時，乙方應即徵得甲方之書面同意，繼續安排未完成之旅遊活動或安排甲方返回。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方怠於安排時，甲方得搭乘相當等級之交通工具自行返回出發地，其所支付之費用，應由乙方負擔。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        第一項延誤行程期間，甲方所支出之食宿或其他必要費用，應由乙方負擔。甲方並得請求依全部旅費除以全部旅遊日數乘以延誤行程日數計算之違約金。延誤行程時數在五小時以上未滿一日者，以一日計算。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 依第一項約定，安排甲方返回時，另應按實計算賠償甲方未完成旅程之費用及由出發地點到第一旅遊地與最後旅遊地返回之交通費用。甲方受有損害者，並得請求賠償。<br>
                      </p>
                      <p>
                        <b>第二十條（旅行業棄置或留滯旅客）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        乙方於旅遊途中，因故意棄置或留滯甲方時，除應負擔棄置或留滯期間甲方支出之食宿及其他必要費用，按實計算退還甲方未完成旅程之費用，及由出發地至第一旅遊地與最後旅遊地返回之交通費用外，並應至少賠償依全部旅遊費用除以全部旅遊日數乘以棄置或留滯日數後相同金額五倍之違約金。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方於旅遊途中，因重大過失有前項棄置或留滯甲方情事時，乙方除應依前項規定負擔相關費用外，並應至少賠償依前項規定計算之三倍違約金。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方於旅遊途中，因過失有第一項棄置或留滯甲方情事時，乙方除應依前項規定負擔相關費用外，並應賠償依第一項規定計算之一倍違約金。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前三項情形之棄置或留滯甲方之時間，在五小時以上未滿一日者，以一日計算；乙方並應儘速依預訂旅程安排旅遊活動，或安排甲方返回。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方受有損害者，另得請求賠償。<br>
                      </p>
                      <p>
                        <b>第二十一條（旅遊途中因非可歸責於旅行業之事由致旅遊內容變更）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        旅遊中因不可抗力或不可歸責於乙方之事由，致無法依預定之旅程、交通、食宿或遊覽項目等履行時，為維護旅遊團體之安全及利益，乙方得變更旅程、遊覽項目或更換食宿、旅程；其因此所增加之費用，不得向甲方收取，所減少之費用，應退還甲方。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方不同意前項變更旅程時，得終止契約，並得請求乙方墊付費用將其送回原出發地，於到達後附加年利率5%利息償還乙方。<br>
                      </p>
                      <p>
                        <b>第二十二條（責任歸屬與協辦）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        旅遊期間，因不可歸責於乙方之事由，致甲方搭乘飛機、輪船、火車、捷運、纜車等大眾運輸工具所受之損害者，應由各該提供服務之業者直接對甲方負責。但乙方應盡善良管理人之注意，協助甲方處理。
                      </p>
                      <p>
                        <b>第二十三條（出發後旅客任意終止契約）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方於旅遊活動開始後，中途離隊退出旅遊活動時，不得要求乙方退還旅遊費用。但乙方因甲方退出旅遊活動後，應可節省或無須支付之費用，應退還甲方。 <br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項情形，乙方並應為甲方安排脫隊後返回出發地之住宿及交通，其費用由甲方負擔。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方於旅遊活動開始後，未能及時參加依本契約所排定之行程者，視為自願放棄其權利，不得向乙方要求退費或任何補償。<br>
                      </p>
                      <p>
                        <b>第二十四條（旅客終止契約後之回程安排）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        甲方於旅遊活動開始後，怠於配合乙方完成旅遊所需之行為致影響後續旅遊行程，而終止契約者，甲方得請求乙方墊付費用將其送回原出發地，於到達後附加年利率5%利息償還之，乙方不得拒絕。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項情形，乙方因甲方退出旅遊活動後，應可節省或無須支出之費用，應退還甲方。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方因第一項事由所受之損害，得向甲方請求賠償。<br>
                      </p>
                      <p>
                        <b>第二十五條（旅行業之協助處理義務）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方在旅遊中發生身體或財產上之事故時，乙方應盡善良管理人之注意為必要之協助及處理。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項之事故，係因非可歸責於乙方之事由所致者，其所生之費用，由甲方負擔。 <br>
                      </p>
                      <p>
                        <b>第二十六條（旅行業應投保責任保險及履約保證保險）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方應依主管機關之規定投保責任保險及履約保證保險。責任保險投保金額：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; <font color="blue">一、 <span style="font-family: SegoeUISymbolRegular">✅</span>︎ 依法令規定 。</font><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 二、 □高於法令規定，金額為：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (一) 每一旅客意外死亡新臺幣___________元。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (二) 每一旅客因意外事故所致體傷之醫療費用新臺幣__________元。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (三) 國內旅遊善後處理費用新臺幣___________元。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (四) 每一旅客證件遺失之損害賠償費用新臺幣__________元。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        乙方如未依前項規定投保者，於發生旅遊事故或不能履約之情形，乙方應以主管機關規定最低投保金額計算其應理賠金額之三倍作為賠償金額。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 乙方應於出團前，告知甲方有關投保旅行業責任保險之保險公司名稱及其連絡方式，以備甲方查詢。<br>
                      </p>
                      <p>
                        <b>第二十七條（購物及瑕疵損害之處理方式）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方不得於旅遊途中，臨時安排甲方購物行程。但經甲方要求或同意者，不在此限。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方安排特定場所購物，所購物品有貨價與品質不相當或瑕疵者，甲方得於受領所購物品後一個月內，請求乙方協助其處理。<br>
                      </p>
                      <p>
                        <b>第二十八條（誠信原則）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        甲乙雙方應以誠信原則履行本契約。乙方依旅行業管理規則之規定，委託他旅行業代為招攬時，不得以未直接收甲方繳納費用，或以非直接招攬甲方參加本旅遊，或以本契約實際上非由乙方參與簽訂為抗辯。<br>
                      </p>
                      <p>
                        <b>第二十九條（消費爭議處理）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 本契約履約過程中發生爭議時，乙方應即主動與甲方協商解決之。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方消費爭議處理申訴（客服）專線或電子信箱：service4@eztravel.com.tw<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方對甲方之消費爭議申訴，應於三個營業日內專人聯繫處理，並依據消費者保護法之規定，自申訴之日起十五日內妥適處理之。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        雙方經協商後仍無法解決爭議時，甲方得向交通部觀光局、直轄市或各縣（市）消費者保護官、直轄市或各縣（市）消費者爭議調解委員會、中華民國旅行業品質保障協會或鄉（鎮、市、區）公所調解委員會提出調解（處）申請，乙方除有正當理由外，不得拒絕出席調解（處）會。<br>
                      </p>
                      <p>
                        <b>第三十條（個人資料之保護）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方因履行本契約之需要，於代辦證件、安排交通工具、住宿、餐飲、遊覽及其所附隨服務之目的內，甲方同意乙方得依法規規定蒐集、處理、傳輸及利用其個人資料。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲方：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; □不同意（甲方如不同意，乙方將無法提供本契約之旅遊服務）。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 簽名：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; <font color="blue"><span style="font-family: SegoeUISymbolRegular">✅</span>︎ 同意。</font><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 簽名： <br>
                        &nbsp; &nbsp; &nbsp; &nbsp; （二者擇一勾選；未勾選者，視為不同意）<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項甲方之個人資料乙方負有保密義務，非經甲方書面同意或依法規規定，不得將其個人資料提供予第三人。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        第一項旅客個人資料蒐集之特定目的消失或旅遊終了時，乙方應主動或依甲方之請求，刪除、停止處理或利用甲方個人資料。但因執行職務或業務所必須或經甲方書面同意，不在此限。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 乙方發現第一項甲方個人資料遭竊取、竄改、毀損、滅失或洩漏時，應即向主管機關通報，並立即查明發生原因及責任歸屬，且依實際狀況採取必要措施。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 前項情形，乙方應以書面、簡訊或其他適當方式通知甲方，使其可得知悉各該事實及乙方已採取之處理措施、客服電話窗口等資訊。<br>
                      </p>
                      <p>
                        <b>第三十一條（合意管轄法院之約定）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲、乙雙方就本契約有關之爭議，以中華民國之法律為準據法。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp;
                        因本契約發生訴訟時，甲乙雙方同意以臺灣臺北地方法院為第一審管轄法院，但不得排除消費者保護法第四十七條或民事訴訟法第四百三十六條之九規定之小額訴訟管轄法院之適用。<br>
                      </p>
                      <p>
                        <b>第三十二條（其他協議事項）</b><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 甲乙雙方同意遵守下列各項：<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 一、 甲方 □同意□不同意 乙方將其姓名提供給其他同團旅客。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 二、 旅遊團費不包含護照費用(或台胞證及台胞證加簽費用)、旅館客房清理及行李小費。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; <font color="blue">三、 乙方對於甲方所提供之個人資料，將依個人資料保護法為完善之保護措施，但因交易行為需求，乙方在處理過程中須將甲方之個資提供給乙方所配合之第三方旅遊必要供應商，包括但不限於航空公司、飯店、保險公司等，以作旅遊目的範圍內之使用。
                        </font><br>
                        &nbsp; &nbsp; &nbsp; &nbsp; 四、 本合約簽約時若與交通部觀光局公布之國內旅遊定型化契約範本或其應記載、不應記載事項相牴觸之處，除甲乙雙方特別協議外，以交通部觀光局為準。<br>
                        &nbsp; &nbsp; &nbsp; &nbsp; <font color="blue">五、 本契約之旅遊費用項目均以團體票或團體人數方式計價，遇個別身分優惠情形(如半票、不占床等)無價差，恕不另退費。
                        </font><br>
                        　 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
                        前項協議事項，如有變更本契約其他條款之規定，除經交通部觀光局核准外，其約定無效，但有利於甲方者，不在此限。<br>
                      </p>

                      <table border="0" width="100%">
                        <tbody><tr height="30">
                          <td colspan="2" height="30"><b></b></td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">甲 方：</td>
                          <td width="40%"></td>
                          <td width="10%" class="contractor-title">乙 方：</td>
                          <td width="40%">OO網旅行社股份有限公司<img src="https://static.cdn-eztravel.com/assets/images/common/big.gif" width="74" height="75" align="absmiddle"></td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">住所地址：</td>
                          <td width="40%"></td>
                          <td width="10%" class="contractor-title">註 冊編 號：</td>
                          <td width="40%">交觀綜字2105 號</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">身分證字號：</td>
                          <td width="40%"></td>
                          <td width="10%" class="contractor-title">負　 責　人：</td>
                          <td width="40%">陳甫彥<img src="https://static.cdn-eztravel.com/assets/images/common/smal.gif" width="56" height="56" align="absmiddle">
                          </td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">電話：</td>
                          <td width="40%"></td>
                          <td width="10%" class="contractor-title">住　　　址：</td>
                          <td width="40%">台北市民生東路三段51號 4樓</td>
                        </tr>
                        <tr height="30">
                          <td width="10%"></td>
                          <td width="40%"></td>
                          <td width="10%" class="contractor-title">電　　　話：</td>
                          <td width="40%">02-25010888</td>
                        </tr>
                        <tr height="30">
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                      
                        <!-- 乙方委託之旅行業副署 -->
                        <!-- defining vendorInfo -->
                        
                        <tr height="30">
                          <td width="100%" colspan="4">乙方委託之旅行業副署：(本契約如係綜合或甲種旅行業自行組團而與旅客簽約者，下列各項免填)</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">公司名稱：</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">註冊編號：</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">負　責　人：</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">住　　　址：</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        <tr height="30">
                          <td width="10%" class="contractor-title">電話或傳真：</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        <tr height="30">
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                          <td width="10%">&nbsp;</td>
                          <td width="40%">&nbsp;</td>
                        </tr>
                        
                        <!-- defining vendorInfo 結束 -->
                      
                        <tr height="80">
                          <td colspan="4" valign="bottom">簽約日期：中華民國　　 　　 年　 　 　月　 　 日<font color="blue">(如未記載，以首次交付金額之日為簽約日期)</font>
                          </td>
                        </tr>
                        <tr height="80">
                          <td colspan="3">簽約地點： </td>
                          <td>
                            <font color="blue">(如未記載，以甲方住（居）所地為簽約地點)</font>
                          </td>
                        </tr>
                        <tr height="30">
                          <td colspan="4" align="left">
                            <font><b>本定型化契約書統一由系統產出，列印後如有手寫填入之內容，需經雙方同意，由甲方簽名並加蓋乙方之公司章始生效力。</b></font>
                          </td>
                        </tr>
                      </tbody></table>
                    </td>
                  </tr>
                </tbody></table>
              </div>
            </div>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
      <b-row class="text-center">
          <b-col>
             <b-form-checkbox
                id="checkbox-1"
                v-model="check_status"
                name="checkbox-1"
                value="accepted"
                unchecked-value="not_accepted"
              >
                <span style="word-wrap:break-word;">我已完整閱讀本服務<b-link type="danger">相關條款</b-link>(含個資聲明)及旅遊契約書，並接受所有規定事項</span>
              </b-form-checkbox>
              <b-alert v-model="showDismissibleAlert" variant="danger" dismissible>
                請先閱讀並確認相關條款
              </b-alert>
          </b-col>
      </b-row>
      <b-row class="text-center pd_20">
        <b-col>
          <div>
            <b-button variant="primary" @click="check_order()">會員購買</b-button>
            <b-button variant="secondary" @click="check_order()">訪客購買</b-button>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>
<script>
  export default {
      data() {
      return {
      showDismissibleAlert: false,
      check_status: 'not_accepted',
       room_selected: 0,
       room_options: [
          { value: '0', text: '0間' },
          { value: '1', text: '1間' },
          { value: '2', text: '2間' },
          { value: '3', text: '3間' },
          { value: '4', text: '4間' },
        ],
       room_selected2: 0,
       room_options2: [
          { value: '0', text: '0間' },
          { value: '1', text: '1間' },
          { value: '2', text: '2間' },
          { value: '3', text: '3間' },
          { value: '4', text: '4間' },
        ],
      }
    },
    methods:{
    //印出dom的内容
    printDomVal(){
      //取得要打印的內容
      let newDomHtml = this.$refs.pdfDom.innerHTML;
      //把要印的html給本頁面
      window.document.body.innerHTML = newDomHtml;
      //調用print
      window.print();
      window.location.reload();   //解決印完按鈕失效的問題
      return false;
    },
    //check_order
    check_order(){
      if(this.check_status=='not_accepted'){
        this.showDismissibleAlert=true;
      }else{
        //繼續購物流程
        this.$router.push(
                { 
                  name: 'order-order_form' , 
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