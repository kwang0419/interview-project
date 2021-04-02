<template>
  <v-app class="app">
    <v-app-bar
      id="header"
      app
      :elevate-on-scroll="isMobile?false:true" :elevation="isMobile?6:1" light
      height="84"
    >
      <v-container>
        <v-row>
          <v-col v-if="isMobile" :cols="2"></v-col>
          <v-col cols="8" md="6">
            <div 
              :class="{ 
                'd-flex':true,
                'align-center':true,
                'justify-center':isMobile
            }">
              <v-img
                alt="Fubon Logo"
                class="shrink"
                contain
                src="./assets/fb_logo.svg"
                transition="scale-transition"
                :style="{'max-width':isMobile?'128.68pt':'204px', 'max-height':isMobile?'27.45pt':'44px'}"
              />
            </div>
          </v-col>
          <v-col :cols="isMobile?2:6" class="text-right pl-1 pr-1" :style="{'padding-top':isMobile?'16px':'12px'}">
            <v-btn
              href="https://me.fubonlife.com.tw/"
              text
              class="pl-0 pr-0"
            >
              <v-img src="./assets/btn_home.svg" :style="{'max-width':isMobile?'25pt':'25px', 'max-height':isMobile?'25pt':'25px'}" alt="回首頁" />
              <span class="pl-1 pt-1 d-md-flex d-none" style="font-size: 16px;">回首頁</span>
            </v-btn>        
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main id="main">
      <v-container :style="{ 'width': '1200', 'padding': isMobile?'0 0 0 0':'6px 12px 28px 12px', 'margin-bottom': isMobile?0:'72px'}">
        <v-row justify="center">
          <v-col>
            <InsuredInfoChangInstruction :isMobile="isMobile" />
            <v-btn
              v-show="showGoTop"
              class="md-5 mr-3 mb-12 pt-2 elevation-1 white--text text-h4"
              :width="isMobile?'59pt':'59px'"
              :height="isMobile?'59pt':'59px'"
              fab
              small
              button
              bottom
              right
              color="#00829B50"
              absolute
              fixed
              @click="goTop"
            >&#8963;
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer id="footer" v-if="!isMobile" absolute padless class="text-center white--text">
      <v-container>
        <v-row>
          <v-col class="pb-1" style="font-size:20px;">
            <div>版權所有 富邦人壽</div>
            <div>最佳瀏覽狀態請使用：Chrome77, Safari 13, Firefox69版本以上</div>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
import InsuredInfoChangInstruction from './components/InsuredInfoChangInstruction.vue';

export default {
  name: 'App',
  components: {
    InsuredInfoChangInstruction,
  },
  data: () => {
    return {
      showGoTop: false,
    }
  },
  computed: {
    isMobile() {
      if (this.$vuetify.breakpoint.xs || this.$vuetify.breakpoint.sm)
      {
        return true;
      }
      return false;
    }
  },
  methods: {
    goTop() {
      window.scrollTo(0,0);
    },
    handleScroll () {
      if (window.scrollY > 200) {
        this.showGoTop = true;
      } else {
        this.showGoTop = false;
      }
    },
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>

<style>
  #main {
    background:#edfbff;
  }
  #main> .v-main__wrap> .container> .row {
    margin-left: 0;
    margin-right: 0;
  }
  #main> .v-main__wrap> .container> .row> .col {
    padding-left: 0;
    padding-right: 0;
  }
  #header {
    background-image: -webkit-linear-gradient(left, #0389D1 0%, #02B6B2 100%);
    background-size: 100% 10%; 
    background-color: white;
  }
  #footer {
    height: 87px;
    background: transparent linear-gradient(90deg, #00829B 0%, #009583 100%) 0% 0% no-repeat padding-box;
    opacity: 1;
  }
</style>

