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
        CardList
    }
}
</script>

<template>
    <div class="container1">
        <form action="/action_page.php">
            <select name="archetype" id="archetype">
                <option value="Alien">Alien</option>
                <option value="Noble Knight">Noble Knight</option>
                <option value="Melodious">Melodious</option>
            </select>
        </form>
        <div class="container2">
            <div class="card_found">Found {{ store.card.length }} Cards</div>
            <CardList></CardList>
        </div>
    </div>
</template>

<style lang="scss">
    .container1{
        position: relative;
        padding: 60px 70px;

        form{
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