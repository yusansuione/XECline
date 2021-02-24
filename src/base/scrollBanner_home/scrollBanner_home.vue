<template>
  <div class="scrollBanner_home">
    <!-- @click="toContactUs" -->
    <div>
      <el-carousel :interval="4000" v-for="(item,index) in homeSliderData" :key="index" type="card" height="400px" trigger="click">
        <el-carousel-item>
          <video-player
            class="video-player vjs-custom-skin"
            ref="videoPlayer"
            :playsinline="true"
            :options="playerOptions2"
          >
          </video-player>
          <!-- <dt>1</dt> -->
        </el-carousel-item>
      </el-carousel>
    </div>
    <div>
      <el-row class="row1-item">
        <el-col :span="5">
          <div class="fl row1-item row1-itemCenter">
            <a href="#row2">
              <dl>
                <dt>数字展馆</dt>
                <dd>为客户创造价值为社会创造效益</dd>
              </dl>
            </a>
          </div>
        </el-col>
        <el-col :span="5">
          <div class="fl row1-item row1-itemCenter">
            <a href="#row3">
              <dl>
                <dt>多媒体应用</dt>
                <dd>为客户创造价值为社会创造效益</dd>
              </dl>
            </a>
          </div>
        </el-col>
        <el-col :span="5">
          <div class="fl row1-item row1-itemCenter">
            <a href="#row4">
              <dl>
                <dt>设计可视化</dt>
                <dd>为客户创造价值为社会创造效益</dd>
              </dl>
            </a>
          </div>
        </el-col>
        <el-col :span="5">
          <div class="fl row1-item row1-itemCenter">
            <a href="#row5">
              <dl>
                <dt>数据可视化</dt>
                <dd>为客户创造价值为社会创造效益</dd>
              </dl>
            </a>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="fl row1-item row1-itemCenter">
            <a href="#row6">
              <dl>
                <dt>创新业务</dt>
                <dd>为客户创造价值为社会创造效益</dd>
              </dl>
            </a>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "scrollBanner_home",
  data(){
      return{
         playerOptions2: {
        autoplay: false,
        muted: false,
        loop: true,
        preload: "auto",
        language: "zh-CN",
        responsive: true,
        muted: false,
        fluid: true,
        sources: [
          {
            type: "video/mp4", // 类型
            // src: require("./img/1546239235065.mp4"), // url地址
          },
        ],
        // poster: require('./img/1546239235065.png'), // 封面地址
        notSupportedMessage: "此视频暂无法播放，请稍后再试",
        controlBar: {
          timeDivider: false,
          durationDisplay: false,
          remainingTimeDisplay: false,
          fullscreenToggle: true,
        },
      },
      }
  },
  props: {
    scrollBanners_home: {
      type: Array,
    },
  },
  methods: {
    toContactUs() {
      this.$router.push("contactUs");
    },
  },
};
</script>

<style scoped lang="scss">
.scrollBanner_home {
  text-align: center;
}
@media all and (max-width: 1920px) {
  img {
    width: 80%;
  }
}
.el-carousel__item video-player {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 0px;
  margin: 0;
}
.video-player {
  width: 100%;
  margin: 10;
}

.row1-item dl {
  float: left;
  width: 100%;
  height: 80px;
  padding: 16px 13px 0 15px;
  color: rgb(255, 253, 253);
  text-align: left;
}
.row1-item dt {
 margin-bottom: 5px;
 font-size: 18px;
}
.row1-item{
  background-color:rgb(71, 106, 170);
}

.el-carousel__item:nth-child(2n) {
  background-color: #e61919;
}

.list-wrap {
    margin-top: 20px;
}

</style>
