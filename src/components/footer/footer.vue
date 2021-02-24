<template>
  <div>
    <div class="footer-top">
      <div class="cf commonWidth">
        <div class="fl footer-top_logo">
          <img src="./logo.jpg" alt="">
        </div>
        <div class="fl footer-top-mL">
          <div class="footer-top_icon footer-top_location"></div>
          <div class="footer-top_info">
            <p>江西萍乡</p>
            <p>莲花县良坊镇</p>
            <p>0001</p>
          </div>
        </div>
        <div class="fl footer-top-mL">
          <div class="footer-top_icon footer-top_phone"></div>
          <div class="footer-top_info">
            <p>010-10086</p>
            <p>022-1008611</p>
            <p>18296160100</p>
          </div>
        </div>
        <div class="fl footer-top-mL">
          <div class="footer-top_icon footer-top_email"></div>
          <div class="footer-top_info">
            <p class="footer-top_emailInfo">wwww.xinyi.pingxiang.com</p>
          </div>
        </div>
        <div class="fl footer-top-mL footer-top_weweima">
          <img :src="bottomCode" alt="">
          <p>关注微信</p>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>京ICP备09061609号-2 Copyright©1999-2021.欣依有限公司 版权所有</p>
    </div>
  </div>
</template>

<script>
  export default {
    created() {
      this.bottomCode = require('common/img/icon-erweima.png')
    }
  }
</script>

<style scoped>
  .footer-top {
    height: 220px;
    background-color: #373d41;
  }

  .footer-top_logo {
    margin: 90px 0 0 30px;
  }

  .footer-top_icon {
    height: 72px;
    background-repeat: no-repeat;
    background-position: center center;
    margin-bottom: 17px;
    margin-top: 42px;
  }

  .footer-top_location {
    background-image: url(./../../common/img/icon-bottom_location.png);
  }

  .footer-top_phone {
    background-image: url(./../../common/img/icon-bottom_phone.png);
  }

  .footer-top_email {
    background-image: url(./../../common/img/icon-bottom_email.png);
  }

  .footer-top_info p {
    height: 24px;
    line-height: 24px;
    font-size: 12px;
    color: #fff;
  }

  .footer-top-mL {
    margin-left: 80px;
  }

  .footer-top_weweima {
    margin-top: 65px;
  }

  .footer-top_weweima p {
    margin-top: 10px;
    color: #fff;
    font-size: 14px;
    text-align: center;
  }

  .footer-top_emailInfo {
    font-size: 16px !important;
    margin-top: 38px;
  }

  .footer-bottom {
    height: 34px;
    line-height: 34px;
    text-align: center;
    font-size: 12px;
    color: #c6c6c6;
    background-color: #2c3235;
  }
</style>
