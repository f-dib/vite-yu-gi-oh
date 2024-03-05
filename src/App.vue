<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import CardContainer from './components/CardContainer.vue';

export default {
    data(){
      return {

        store,

        isLoading: true

      }
    },
    created(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0').then(res => {
        this.store.card = res.data,
        this.isLoading = false
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
    <div v-if="isLoading" class="load">
      Loading...
    </div>
    <div v-else>
      <CardContainer></CardContainer>
    </div>
</template>

<style lang="scss">
  @use './general.scss' as *;

  .load{
    color: black;
    text-align: center;
    padding: 50px;
  }
</style>