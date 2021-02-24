<template>
  <!-- <div class="companyProfile" style="height:100%;">
    <div class="commonWidth cf" style="height:100%;">
      <div class="fl row2-img-wrap"
           :class="'row2-img'+(index+1)"
           v-for="(item,index) in homeSliderData"
           :key="index">
        <div class="bgColor">
          <div class="top" :class="'row2-img'+(index+1)+'_top'">
            <div></div>
            <p>{{item.title}}</p>
          </div>
          <div class="bottom hide">
            <p>{{item.instruction1}}</p>
            <p>{{item.instruction2}}</p>
            <p>{{item.instruction3}}</p>
           <input type="button" value="查看详情">
          </div>
        </div>
      </div>
    </div>
  </div> -->
  <div class="c-content">
      <el-row class="list-wrap">
        <ul class="c-list" >
          <li>
            <video-player
              class="vjs-custom-skin"
              ref="videoPlayer"
              :playsinline="true"
              :options="playerOptions"
            >
            </video-player>
          </li>
          <li>
            <video-player
              class="vjs-custom-skin"
              ref="videoPlayer"
              :playsinline="true"
              :options="playerOptions"
            >
            </video-player>
          </li>
        </ul>
      </el-row>
    </div>
</template>

<script>
  export default {
    name: 'digitalPavilion',
    props: {
      homeSliderData: {
        type: Array,
        default: function(){
          
          return new Array[1];
        }
      }
    },
    data(){
      return{
        playerOptions: {
        playbackRates: [0.5, 1.0, 1.5, 2.0],
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
            // src: require(""), // url地址
          },
        ],
        // poster: require('./img/1546239235065.png'), // 封面地址
        notSupportedMessage: "此视频暂无法播放，请稍后再试",
        controlBar: {
          timeDivider: true,
          durationDisplay: true,
          remainingTimeDisplay: false,
          fullscreenToggle: true,
        },
      },
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
    }
  }
</script>

<style scoped lang="scss">
  .row2-img1 {
    width: 240px;
    height: 100%;
    background: url(./../../assets/home-img/img-ruanjian.png);
  }

  .row2-img1_top div {
    height: 57px;
    margin-top: 130px;
    margin-bottom: 68px;
    background: url(./../../assets/home-img/icon-ruanjian.png) no-repeat center center;
  }

  .row2-img1_top p {
    font-size: 22px;
    color: #fff;
    text-align: center;
    font-weight: bold;
  }

  .row2-img2 {
    width: 240px;
    height: 100%;
    background: url(./../../assets/home-img/img-icp.png);
  }

  .row2-img2_top div {
    height: 57px;
    margin-top: 130px;
    margin-bottom: 68px;
    background: url(./../../assets/home-img/icon-icp.png) no-repeat center center;
  }

  .row2-img2_top p {
    font-size: 22px;
    color: #fff;
    text-align: center;
    font-weight: bold;
  }

  .row2-img3 {
    width: 240px;
    height: 100%;
    background: url(./../../assets/home-img/img-idc.png);
  }

  .row2-img3_top div {
    height: 57px;
    margin-top: 130px;
    margin-bottom: 68px;
    background: url(./../../assets/home-img/icon-idc.png) no-repeat center center;
  }

  .row2-img3_top p {
    font-size: 22px;
    color: #fff;
    text-align: center;
    font-weight: bold;
  }

  .row2-img4 {
    width: 240px;
    height: 100%;
    background: url(./../../assets/home-img/img-data.png);
  }

  .row2-img4_top div {
    height: 57px;
    margin-top: 130px;
    margin-bottom: 68px;
    background: url(./../../assets/home-img/icon-data.png) no-repeat center center;
  }

  .row2-img4_top p {
    font-size: 22px;
    color: #fff;
    text-align: center;
    font-weight: bold;
  }

  .row2-img5 {
    width: 240px;
    height: 100%;
    background: url(./../../assets/home-img/img-web.png);
  }

  .row2-img5_top div {
    height: 57px;
    margin-top: 130px;
    margin-bottom: 68px;
    background: url(./../../assets/home-img/icon-web.png) no-repeat center center;
  }

  .row2-img5_top p {
    font-size: 22px;
    color: #fff;
    text-align: center;
    font-weight: bold;
  }

  .row2-img-wrap {
    overflow: hidden;
  }

  .row2-img-wrap .top {
    -webkit-transition: .5s;
    -moz-transition: .5s;
    -ms-transition: .5s;
    -o-transition: .5s;
    transition: .5s;
  }

  .row2-img-wrap .bottom {
    margin-top: 42px;
    text-align: center;
  }

  .row2-img-wrap .bottom p {
    height: 24px;
    line-height: 24px;
    color: #fff;
  }

  .row2-img-wrap .bottom input {
    width: 105px;
    height: 32px;
    line-height: 32px;
    text-align: center;
    color: #fff;
    border: 1px solid #fff;
    background-color: rgba(0, 223, 255, .9);
    margin-top: 42px;
    cursor: pointer;
  }

  .row2-img-wrap:hover .bgColor {
    width: 100%;
    height: 100%;
    background-color: rgba(0, 223, 255, .7);
    border: 1px solid rgba(0, 223, 255, .7);
  }

  .row2-img-wrap:hover .top {
    margin-top: -80px;
  }

  .row2-img-wrap:hover .bottom {
    display: block;
  }
  ul.c-list {
    height: 100%;
    margin: 0 auto;
}
ul {
    display: block;
    list-style-type:  none;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    padding-inline-start: 40px;
}
li{
    width: 657px;
    height: 305px;
    float:left;
    margin-left:20px;
}
.c-content{
  min-width: 1200px;
}
</style>
