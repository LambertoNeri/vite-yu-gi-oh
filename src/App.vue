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
      axios.all([
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?fname=Magician'),
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      ])
      .then(responseArr => {
      console.log('Date created: ', responseArr[0].data.data);
      console.log('Date created: ', responseArr[1].data);
      this.store.cardList = responseArr[0].data.data
      this.store.archetypeList = responseArr[1].data
      });
    }
     /* axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then(response => (this.store.cardList = response.data.data));
    }, */
  }
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss" >
  @use '../src/assets/styles/general.scss' as *;

  
  
</style>
