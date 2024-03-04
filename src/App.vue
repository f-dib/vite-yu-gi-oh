<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import CardList from './components/CardList.vue';

export default {
  data(){
    return {

      store
      
    }
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
      this.store.card = res.data.data
      console.log(this.store.card)
    })
  },
  components: {
    AppNav,
    CardList
  }
}
</script>

<template>
  <CardList></CardList>
</template>

<style lang="scss">
  @use './general.scss' as *;
</style>