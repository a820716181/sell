<template>
  <div class="tab">
    <div class="tab-item">
      <router-link to="/goods">{{goods}}</router-link></div>
    <div class="tab-item">
      <router-link to="ratings">{{ratings}}</router-link></div>
    <div class="tab-item">
      <router-link to="/seller">{{seller}}</router-link></div>
  </div>
</template>
<script>
  export default {
    name: 'tabbar',
    data() {
      return {
        goods: '商品',
        ratings: '评价',
        seller: '商家'
      };
    }
  };
</script>
<style scoped>
  .tab {
    display: flex;
    width: 100%;
    height: 40px;
    line-height: 40px;
  }
  .tab-item {
    flex: 1;
    text-align: center;
  }
  .tab-item a {
    display: block;
    font-size: 14px;
    color: rgb(77,85,93);
  }
  .tab-item a.active {
    color: #f01414;
  }
</style>
