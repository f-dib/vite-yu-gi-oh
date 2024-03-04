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
        <div v-for="currentCard in store.card" class="flex-column card_style">
            <div>
                <img class="img_fluid" :src="currentCard.card_images[0].image_url" alt="">
            </div>
            <div>
                {{ currentCard.name }}
            </div>
            <div>
                {{ currentCard.archetype }}
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    .card_style {
        width: calc(100% / 5);
    }
</style>