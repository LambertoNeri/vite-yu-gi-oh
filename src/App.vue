<script>
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';
  import AppFooter from './components/AppFooter.vue';
  import axios from 'axios';
  import { store } from './store'



  export default {
    data() {
      return {
        store,
      };
    },
    components: {
      AppHeader,
      AppMain,
      AppFooter,
    },
    created() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then(response => (this.store.cardList = response.data.data));
    },
  }
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss" >
  @use '../src/assets/styles/general.scss' as *;

  
  
</style>
