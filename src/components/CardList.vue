<script>
import { store } from '../store.js';
export default {
    name: 'CardList',

    data(){
        return {
            store
        }
    }
}
</script>

<template>
    <div class="d-flex">
        <div v-for="currentCard in store.card.data" class="flex-column card_style">
            <div>
                <img class="img_fluid" :src="currentCard.card_images[0].image_url" alt="">
                <div class="flex-column card_description">
                    <h3>{{ currentCard.name }}</h3>
                    <span>{{ currentCard.archetype }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    .card_style {
        width: calc(100% / 5 - 10px / 5 * 4);

        text-align: center;
        background-color: #d48f38;

        .card_description{

            padding: 10px;

            img{
                margin-bottom: 15px;
            }
    
            h3{
                color: white;
                margin-bottom: 20px;
            }
        }

    }
</style>