<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import CardContainer from './components/CardContainer.vue';
import ArchetypeSearch from './components/ArchetypeSearch.vue';

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
        this.isLoading = false,

        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res2 => {
        this.store.allArchetype = res2.data
        })
      }).catch(err => {
        console.log(err)
      })
    },
    methods: {

      searchType(){

        if (this.store.searchArchetype == '0'){
          axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0').then(res => {
            this.store.card = res.data
        })
        } else {
          
          axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=' + this.store.searchArchetype).then(res => {
            this.store.card = res.data
          })

        }

      }
      
    },
    components: {
      AppNav,
      CardContainer,
      ArchetypeSearch
    }
}
</script>

<template>
    <AppNav></AppNav>
    <div v-if="isLoading" class="load">
      Loading...
    </div>
    <div v-else>
      <ArchetypeSearch class="form" @onchange="searchType()"></ArchetypeSearch>
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

  .form{
    position: absolute;
    left: 70px;
    top: 140px;
    transform: translateY(-50%);
  }
</style>