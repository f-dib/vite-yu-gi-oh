<script>
import { store } from '../store.js';
import CardList from './CardList.vue';

export default {
    name: 'CardContainer',

    data(){
        return {
            store
        }
    },
    components: {
        CardList,
    }
}
</script>

<template>
    <div class="container1">
        <div class="container2">
            <div class="card_found">Found {{ store.card.data.length }} Cards</div>
            <CardList></CardList>
        </div>
    </div>
</template>

<style lang="scss">
    .container1{
        padding: 60px 70px;

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