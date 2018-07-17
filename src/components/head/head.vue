<template>
  <div class="header">
    <div class="content_wrapper">
      <div class="avatar">
        <img :src="seller.avatar" alt="" width="64" height="64">
      </div>
      <div class="content">
        <div class="title">
          <span class="brand"></span>
          <span class="name">{{seller.name}}</span>
        </div>
        <div class="description">
          {{seller.description}}/{{seller.deliveryTime}}分钟送达
        </div>
        <div v-if="seller.supports" class="support">
            <span class="icon"></span>
            <span class="text">{{seller.supports[0].description}}</span>
        </div>
      </div>
      <div v-if="seller.supports" class="support-count" @click="showDetail">
        <span class="count">{{seller.supports.length}}个</span>
        <i class="icon-keyboard_arrow_right"></i>
      </div>
    </div>
    <div class="bulletin-wrapper" @click="showDetail">
      <span class="bulletin-title"></span><span class="bulletin-text">{{seller.bulletin}}</span>
      <i class="icon-keyboard_arrow_right"></i>
    </div>
    <div class="background">
      <img :src="seller.avatar" width="100%" height="100%" alt="">
    </div>
    <div v-show="detailShow" class="detail">
      <div class="detail-wrapper clearfix">
        <div class="detail-main">
          <h1 class="name">{{seller.name}}</h1>
        </div>
      </div>
      <div class="detail-close">
        <span class="icon-close">X</span>
      </div>
    </div>
  </div>
</template>

<script>
  import star from 'components/star/star';

  export default {
    name: 'headd',
    props: {
      seller: {
        type: Object
      }
    },
    data() {
      return {
        detailShow: false
      };
    },
    methods: {
      showDetail() {
        this.detailShow = true;
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style type="text/ecmascript-6">
  .header {
    position: relative;
    overflow: hidden;
    color: #fff;
    background: rgba(7,17,27,0.5);
  }
  .content_wrapper {
    position: relative;
    padding: 24px 12px 18px 24px;
    font-size: 0;
  }
  .avatar {
    position: relative;
    display: inline-block;
    vertical-align: top;
  }
  .avatar>img {
    border-radius: 2px;
  }
  .content {
    display: inline-block;
    margin-left: 16px;
  }
  .title {
    margin: 2px 0 8px 0;
  }
  .brand {
    display: inline-block;
    vertical-align: top;
    width: 30px;
    height: 18px;
    background-image: url("brand@3x.png");
    background-size: 30px 18px;
    background-repeat: no-repeat;
  }
  .name {
    margin-left: 6px;
    font-size: 16px;
    line-height: 18px;
    font-weight: bold;
  }
  .description {
    margin-bottom: 10px;
    line-height: 12px;
    font-size: 12px;
  }
  .icon {
    display: inline-block;
    vertical-align: top;
    width: 12px;
    height: 12px;
    margin-right: 4px;
    background: url("decrease_1@3x.png");
    background-size: 12px 12px;
    background-repeat: no-repeat;
  }
  .text {
    line-height: 12px;
    font-size: 12px;
  }
  .support-count {
    position: absolute;
    right: 12px;
    bottom: 14px;
    padding: 0 8px;
    height: 24px;
    line-height: 24px;
    border-radius: 14px;
    background-color: rgba(0,0,0,0.2);
    text-align: center;

  }
  .count {
    vertical-align: top;
    font-size: 10px;
  }
  .icon-keyboard_arrow_right {
    margin-left: 2px;
    line-height: 24px;
    font-size: 10px;
  }
  .bulletin-wrapper {
    position: relative;
    height: 28px;
    line-height: 28px;
    padding: 0 22px 0 12px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    background: rgba(7,17,27,0.2);
  }
  .bulletin-title {
    display: inline-block;
    margin-top: 8px;
    vertical-align: top;
    width: 22px;
    height: 12px;
    background: url("bulletin@3x.png");
    background-size: 22px 12px;
    background-repeat: no-repeat;
  }
  .bulletin-text {
    vertical-align: top;
    margin: 0 4px;
    font-size: 10px;
  }
  .bulletin-title>.icon-keyboard_arrow_right{
    position: absolute;
    font-size: 10px;
    right: 12px;
    top: 8px;
  }
  .background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    filter: blur(10px);
  }
  .detail {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 100;
    width: 100%;
    height: 100%;
    overflow: auto;
    background: rgba(7,17,27,.8);
  }
  .clearfix {
    display: inline-block;
  }
  .clearfix:after {
    display: block;
    content: ".";
    height: 0;
    line-height: 0;
    clear: both;
    visibility: hidden;
  }
  .detail-wrapper {
    width: 100%;
    min-height: 100%;
  }
  .detail-main {
    margin-top: 64px;
    padding-bottom: 64px;
  }
  .detail-close {
    position: relative;
    width: 32px;
    height: 32px;
    margin: -64px auto;
    clear: both;
    font-size: 32px;
  }
  .detail-main>.name {
    line-height: 16px;
    text-align: center;
    font-size: 16px;
    font-weight: 700;
  }
</style>
