<template>
  <div class="header-bottom">
    <div class="cf commonWidth">
      <img class="fl header-bottom_img" v-lazy="iconLogo" alt="" />
      <div class="fr">
        <ul id="routerWrap">
          <router-link
            @mouseenter.native="addClas(item.name)"
            @click.native="clilckAddClas($event, item.name)"
            v-for="(item, index) in nav"
            tag="li"
            :to="item.url"
            ref="routerLink"
            :key="index"
          >
            {{ item.name }}
          </router-link>
        </ul>
      </div>
    </div>
    <div
      class="header-bottom-subTab hide"
      :class="{ show: nav_active === '关于我们' }"
    >
      <ul class="cf">
        <router-link tag="li" to="/introduce">企业简介</router-link>
        <router-link tag="li" exact to="/managementTeam">新闻中心</router-link>
        <router-link tag="li" exact to="/developmentCatalogue"
          >发展历程</router-link
        >
        <router-link tag="li" to="/qualificationHonor">资质荣誉</router-link>
        <!-- <router-link tag="li" to="/culture">企业文化</router-link> -->
      </ul>
      <div class="sliderBorder"></div>
    </div>
    <div
      class="header-bottom-subTab hide"
      :class="{ show: nav_active === '数字展馆' }"
    >
      <ul class="cf">
        <router-link tag="li" to="/introduce">城市馆</router-link>
        <router-link tag="li" exact to="/managementTeam">特色小镇/产业园 </router-link>
        <router-link tag="li" exact to="/developmentCatalogue"
          >智慧城市</router-link
        >
        <router-link tag="li" to="/qualificationHonor">企业展馆</router-link>
        <router-link tag="li" to="/culture">商业营销厅</router-link>
        <router-link tag="li" to="/culture">博物馆</router-link>
      </ul>
      <div class="sliderBorder"></div>
    </div>
       <div
   class="header-bottom-subTab hide"
   :class="{ show: nav_active === '多媒体应用' }"
 >
   <ul class="cf">
     <router-link tag="li" to="/introduce">城市形象设计</router-link>
     <router-link tag="li" exact to="/managementTeam">数字影院 </router-link>
     <router-link tag="li" exact to="/developmentCatalogue"
       >影视动画</router-link
     >
     <router-link tag="li" to="/qualificationHonor">互动多媒体</router-link>
     <router-link tag="li" to="/culture">大型Show策划</router-link>
   </ul>
   <div class="sliderBorder"></div>
    </div>
    <div
  class="header-bottom-subTab hide"
  :class="{ show: nav_active === '设计可视化' }"
>
  <ul class="cf">
    <router-link tag="li" to="/introduce">效果图</router-link>
    <router-link tag="li" exact to="/managementTeam">三维动画</router-link>
    <router-link tag="li" exact to="/developmentCatalogue"
      >多媒体视频</router-link
    >
    <router-link tag="li" to="/qualificationHonor">360全景/VR/AR</router-link>
  </ul>
  <div class="sliderBorder"></div>
  </div>
     <div
 class="header-bottom-subTab hide"
 :class="{ show: nav_active === '数据可视化' }"
>
 <ul class="cf">
   <router-link tag="li" to="/introduce">数据可视化</router-link>
 </ul>
 <div class="sliderBorder"></div>
 </div>
     <div
class="header-bottom-subTab hide"
:class="{ show: nav_active === '联系我们' }"
>
<ul class="cf">
  <router-link tag="li" to="/introduce">联系我们</router-link>
  <router-link tag="li" to="/introduce">招贤纳士</router-link>
</ul>
<div class="sliderBorder"></div>
</div>
  </div>
</template>
<script>
export default {
  name: "home-nav",
  data() {
    return {
      nav: [
        { name: "首页", url: "/index" },
        { name: "关于我们", url: "/introduce" },
        { name: "数字展馆", url: "/product" },
        { name: "多媒体应用", url: "/successCase" },
        { name: "设计可视化", url: "/newsCenter" },
        { name: "数据可视化", url: "/recruitment" },
        { name: "创新业务", url: "/recruitment" },
        { name: "联系我们", url: "/contactUs" },
      ],
      nav_active: "首页",
      click_active: "",
    };
  },
  methods: {
    addClas(name) {
      this.nav_active = name;
    },
    clilckAddClas(ev, name) {
      let routes = document
        .getElementById("routerWrap")
        .getElementsByTagName("li");
      this.click_active = name;
      if (this.click_active === "关于我们") {
        ev.target.setAttribute("id", "routerActive");
      } else {
        for (let i = 0; i < routes.length; i++) {
          routes[i].setAttribute("id", "");
        }
      }
    },
  },
  created() {
    this.iconLogo = require("common/img/icon-logo.png");
  },
};
</script>

<style scoped lang="scss">
.header-bottom {
  height: 93px;
  .commonWidth ul {
    margin-top: 46px;
    #routerActive {
      color: #0051bc;
      border-bottom: 2px solid #0044b4;
      padding-bottom: 8px;
    }
    li {
      float: left;
      height: 27px;
      line-height: 27px;
      font-size: 16px;
      color: #000000;
      padding: 0 15px;
      text-decoration: none;
      border: 1px solid #fff;
      cursor: pointer;
      margin-left: 8px;
      transition: 0.5s;
      &:hover {
        color: #005bf5;
      }
      &.router-link-active {
        color: #0051bc;
        border-bottom: 2px solid #0044b4;
        padding-bottom: 8px;
      }
    }
  }
}

.header-bottom-subTab {
  position: absolute;
  left: 0;
  top: 125px;
  z-index: 9;
  width: 100%;
  height: 52px;
  line-height: 52px;
  background-color: rgba(0, 0, 0, 0.3);
  ul {
    margin-left: 30%;
    li {
      float: left;
      color: #fff;
      margin-right: 62px;
      cursor: pointer;
      &.router-link-active {
        color: #00d8ff;
      }
      &:hover {
        color: #00d8ff;
      }
    }
  }
  &:hover .sliderBorder {
    width: 99%;
    border-width: 1px;
  }
}

.header-bottom_img {
  margin-top: 21px;
}

.sliderBorder {
  border: 0 dotted #0abdff;
  width: 0;
  margin: 0 auto;
  transition: 1s;
}
</style>
