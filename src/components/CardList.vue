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
    <ul>
        <li v-for="currentCard in store.card">
        {{ currentCard.name }}
        </li>
    </ul>
</template>

<style lang="scss">
</style>