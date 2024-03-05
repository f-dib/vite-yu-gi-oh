<script>
import { store } from '../store.js';
import CardList from './CardList.vue';
import ArchetypeSearch from './ArchetypeSearch.vue'

export default {
    name: 'CardContainer',

    data(){
        return {
            store
        }
    },
    components: {
        CardList,
        ArchetypeSearch
    }
}
</script>

<template>
    <div class="container1">
        <ArchetypeSearch class="form"></ArchetypeSearch>
        <div class="container2">
            <div class="card_found">Found {{ store.card.data.length }} Cards</div>
            <CardList></CardList>
        </div>
    </div>
</template>

<style lang="scss">
    .container1{
        position: relative;
        padding: 60px 70px;

        .form{
            position: absolute;
            left: 70px;
            top: 30px;
            transform: translateY(-50%);
        }

        .container2{
            padding: 30px;
            background-color: white;
            color: black;

            .card_found{
                padding: 10px;
                color: white;
                background-color: black;
            }
        }
    }
</style>