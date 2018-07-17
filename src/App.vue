<template>
  <div id="app">
    <v-head :seller="seller"></v-head>
    <v-tabbar></v-tabbar>
    <router-view></router-view>
  </div>
</template>
<script>
  import head from './components/head/head';
  import tabbar from './components/tabbar/tabbar';

  const ERR_OK = 0;
  export default {
    data() {
      return {
        seller: {}
      };
    },
    created() {
      this.$http.get('/api/seller').then((response) => {
        response = response.body;
        if (response.errno === ERR_OK) {
            this.seller = response.data;
        }
      });
    },
    name: 'App',
    components: {
     'v-head': head,
      'v-tabbar': tabbar
    }
  };
</script>
<style>
</style>
