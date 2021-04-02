<template>
  <v-card id="card-instruction">
    <v-container :class="{ step:true, 'pt-5':isMobile, 'pb-5':isMobile }">
      <v-row no-gutters>
        <v-col>
          <span>&#9646;</span>
          <span 
            v-if="isMobile" class="font-weight-medium"
            style="font-size: 24pt;font-family: PingFangTC-Medium, sans-serif;">
            多張保單地址/電話/E-mail變更
          </span>
          <span v-else style="font-size: 27px;font-family: Source Sans Pro">
            變更流程
          </span>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="step" :style="{stepStyle:true, 'border-top':isMobile?'1px dashed #EDEDED':'none', 'margin-top':isMobile?'13.7pt':'22px'}">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 1 :</span></div>
          <div v-if="isMobile" :style="stepDescriptFont">
            由【手機e方便】，點選『保戶會員專區』登入。
          </div>
          <div v-else :style="stepDescriptFont">
            由【富邦人壽官網】，點選『保戶會員專區』登入。
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile01.png" width="305" height="542" :class="imageStyle" :style="{'margin-bottom':isMobile?'20px':'16px'}"></v-img>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile02.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web01.png" width="810" height="456" class="mb-4" :class="imageStyle"></v-img>
          <v-img src="../assets/web/web02.png" width="810" height="456" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 2 :</span></div>
          <div :style="stepDescriptFont">
            <div>點選『線上交易』</div>
            <table>
              <tr style="vertical-align:top">
                <td>&#9733;</td>
                <td>保戶需先申請成為交易會員方可於網路 辦理變更
                  <span v-if="isMobile">。</span>
                  <span v-else>&#65377;&#65377;</span>
                </td>
              </tr>
            </table>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile03.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web03.png" width="810" height="788" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 3 :</span></div>
          <div :style="stepDescriptFont">
            <div>點選後進入『多張保單地址/電話/E-mail變更』作業。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile04.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web04.png" width="810" height="456" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 4 :</span></div>
          <div :style="stepDescriptFont">
            <div>
              確認顯示的行動電話及電子信箱是否為最新資料，若需修改請點選
              <v-img v-if="isMobile" src="../assets/edit_btn.svg" style="width: 23pt; height:22pt; display:inline-flex;"></v-img>
              <v-img v-else width="14px" src="../assets/editpen_icon.svg" style="width: 14px!important; height 21px; box-shadow:none; border: 0; display:inline-flex;"></v-img>
              修改。
            </div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile05.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web05.png" width="810" height="456" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 5 :</span></div>
          <div :style="stepDescriptFont">
            <div>
              請點選 
              <v-img v-if="isMobile" src="../assets/edit_btn.svg" style="width: 23pt; height:22pt; display:inline-flex;"></v-img>
              <v-img v-else width="14px" src="../assets/editpen_icon.svg" style="width: 14px!important; height 21px; box-shadow:none; border: 0; display:inline-flex;"></v-img>
              即可輸入欲變更之內容
            </div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile06.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols"  class="img-web-col">
          <v-img src="../assets/web/web06.png" width="810" height="753" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 6 :</span></div>
          <div :style="stepDescriptFont">
            <table v-if="isMobile">
              <tr style="vertical-align:top">
                <td><span style="background: #F55A08; color: white; padding: 0 0 0 12px; border-radius: 5px; margin-left: -28px; margin-right: 6px; justify: start;">1、</span></td>
                <td><span style="margin-left:-4px;">請確認變更內容是否正確</span></td>
              </tr>
              <tr style="vertical-align:top">
                <td><span style="background: #F55A08; color: white; padding: 0 0 0 12px; border-radius: 5px; margin-left: -28px; margin-right: 6px; justify: start;">2、</span></td>
                <td><span style="margin-left:-4px;">若欲放棄申請，可點選 <v-img width="22pt" height="22pt" src="../assets/delete_btn.svg" style="border: 0; display:inline-flex; margin: 0; text-align: justify;"></v-img></span></td>
              </tr>
              <tr style="vertical-align:top">
                <td><span style="background: #F55A08; color: white; padding: 0 0 0 12px; border-radius: 5px; margin-left: -28px; margin-right: 6px; justify: start;">3、</span></td>
                <td><span style="margin-left:-4px;">若欲修改該項目變更輸入內容，可點選 <v-img width="23pt" height="22pt" src="../assets/edit_btn.svg" style="border: 0; display:inline-flex; margin: 0; text-align: justify;"></v-img></span></td>
              </tr>
            </table>

            <table v-else>
              <tr>
                <td><span style="background: #F55A08; color: white; padding: 0 14px; border-radius: 5px; margin-left: -36px; margin-right:8px; justify: start;">1</span></td>
                <td>確認變更內容</td>
              </tr>
              <tr>
                <td><span style="background: #F55A08; color: white; padding: 0 14px; border-radius: 5px; margin-left: -36px; margin-right:8px; justify: start;">2</span></td>
                <td>
                  點選 <v-img src="../assets/delete_btn.svg" style="width: 23px; height 22px; box-shadow:none; border: 0; display:inline-flex;"></v-img>，即可刪除此項目
                </td>
              </tr>
              <tr>
                <td><span style="background: #F55A08; color: white; padding: 0 14px; border-radius: 5px; margin-left: -36px; margin-right:8px; justify: start;">3</span></td>
                <td>
                  點選 
                  <v-img src="../assets/edit_btn.svg" style="width: 23px; height 22px; box-shadow:none; border: 0; display:inline-flex;"></v-img>
                  可回此變更項目輸入修改變更內容
                </td>
              </tr>
            </table>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile07.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web07.png" width="810px" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 7 :</span></div>
          <div :style="stepDescriptFont">
            <div :style="{'font-family':isMobile?'PingFangTC-Regular':'Helvetica, sans-serif'}">請審閱重要提醒, 確認無誤後請勾選 &#9744;我已了解並同意後, 點選確認進入下一步&#65377;</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img  src="../assets/mobile/mobile08.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img  src="../assets/web/web08.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 8 :</span></div>
          <div>
            <div :style="stepDescriptFont">請確認本次辦理變更資料，是否傳送至其他保險公司申辦相同變更項目。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile09.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web09.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 9 :</span></div>
          <div :style="stepDescriptFont">
            <div>如同意傳送至其他保險公司，請選擇欲傳送之保險公司(可複選)。</div>
            <div>&#9733;僅提供有加入試辦之保險公司，請勾選有該公司保單之保險公司。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile10.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web10.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>  

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 10 :</span></div>
          <div>
            <div :style="stepDescriptFont">請審閱保全申請轉送暨個人資料告知事項，審閱完成後，請點選&#9744;本人已審閱蒐集、處理及利用個人資料告知事項，如取消轉送，請點選『不同意傳送』，可回至確認是否同意轉送頁重新選擇。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile11.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web11.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 11 :</span></div>
          <div>
            <div :style="stepDescriptFont">輸入動態密碼，未收到動態密碼，可點選重新發送動態密碼。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile12.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web12.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <hr :class="hrStyle">
    <v-container class="step" :style="stepStyle">
      <v-row no-gutters>
        <v-col :cols="descripCols">
          <div><span :style="stepTitleFont">步驟 12 :</span></div>
          <div>
            <div :style="stepDescriptFont">委託受理完成。<br v-if="isMobile">可點選『列印內容』，產出加密之PDF檔，密碼為要保人身分證字號，第一個英文字母大寫。</div>
          </div>
        </v-col>
        <v-col v-if="isMobile" :cols="imageCols">
          <v-img src="../assets/mobile/mobile13.png" width="305" height="542" :class="imageStyle"></v-img>
        </v-col>
        <v-col v-else :cols="imageCols" class="img-web-col">
          <v-img src="../assets/web/web13.png" width="810" :class="imageStyle"></v-img>
        </v-col>
      </v-row>
    </v-container>  
  </v-card>
</template>

<script>
export default {
  props: ['isMobile'],
  computed: {
    descripCols(){
      if (this.isMobile) {
        return 12;
      }
      return 3;
    },
    imageCols(){
      if (this.isMobile) {
        return 12;
      }
      return 9;
    },
    imageStyle() {
      if (this.isMobile) {
        return 'mobile-image';
      }
      return 'web-image';
    },
    fontSize() {
      if (this.isMobile) {
        return '26pt';
      }
      return '10pt';
    },
    stepStyle() {
      if (this.isMobile) {
        return {
          'padding': '0'
        }
      }
      return {
        'padding':'0 0 9px 0'
      }
    },
    stepTitleFont() {
      if (this.isMobile) {
        return {
          'font-family':'PingFangTC-Medium',
          'font-size': '18pt',
        }
      }
      return {
        'font-family':'PingFangTC-Regular',
        'font-size': '18px',
      }
    },
    stepDescriptFont() {
      if (this.isMobile) {
        return {
          'font-family':'PingFangTC-Regular',
          'font-size':'18pt',
          'padding-right':'0'
        }
      }
      return {
        'font-family':'PingFangTC-Regular',
        'font-size': '18px',
      }
    },
    hrStyle() {
      if (this.isMobile) {
        return 'mobile-dashed-hr';
      }
      return 'web-dashed-hr';
    },
  }
}
</script>

<style>

#card-instruction {
  padding-top: 16px;
  padding-left: 15px;
  padding-right: 15px;
  box-shadow: none;
}
.step>.row>.col:first-child:not(:first-of-type(.container)) {
  padding-right: 0px;
  max-width: 294px;
}

.step:first-child>.row>.col {
  height: 38px;
  font: var(--unnamed-font-style-normal) normal var(--unnamed-font-weight-normal) var(--unnamed-font-size-27)/var(--unnamed-line-spacing-34) var(--unnamed-font-family-source-sans-pro);;
  letter-spacing: var(--unnamed-character-spacing-0);
  text-align: left;
  font: normal normal normal 27px/34px Source Sans Pro;
  letter-spacing: 0px;
  color: #00829B;
  opacity: 1;
}

.step:first-child>.row>.col>span:first-child{
  width: 8px;
  height: 24px;
  background: #00829B 0% 0% no-repeat padding-box;
  opacity: 1;
  margin-left: -10px;
  margin-right: 8px;
}

.step>.row>.col>div:first-child>span {
  color: #F55A08;
  padding-bottom: 9px;
}
.step>.row>.col>div:first-child>span::before {
  content: "\25b6";
  color: #F55A08;
  padding-left: 0px;
  padding-right: 20px;
  font-size: 15pt;
}
.step>.row>.col>div:nth-child(2) {
  padding: 0 20px 0 36px;
  color: #505050;
}

.step:last-child .row .col:last-child {
  padding-bottom: 55px;
}
.mobile-dashed-hr {
  border-top: 1px dashed #EDEDED;
  margin-bottom: 17.2pt;
}
.web-dashed-hr {
  border-top: 1px dashed #EDEDED;
  margin-bottom: 21.5px;
}


.step .col .v-image {
  opacity: 1;
  margin-left: auto !important;
  margin-right: auto !important;
}
.mobile-image {
  margin-bottom: 32.28pt;
  margin-top: 8pt;
}
.web-image {
  margin-bottom: 18px;
}

.img-web-col {
  padding-right: 22px!important;
}
.img-web-col:not(.img-web-col:last-child) {
  margin-bottom: 34px;
}

.v-responsive__content {
  width: 810px!important;
}
</style>