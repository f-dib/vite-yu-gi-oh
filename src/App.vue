<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import CardContainer from './components/CardContainer.vue';

export default {
  data(){
    return {

      store

    }
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0').then(res => {
      this.store.card = res.data.data
    })
  },
  components: {
    AppNav,
    CardContainer
  }
}
</script>

<template>
  <AppNav></AppNav>
  <CardContainer></CardContainer>
</template>

<style lang="scss">
  @use './general.scss' as *;
</style>