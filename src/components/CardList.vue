<script>
export default {
    name: 'CardList',

    props: {
        card: Array,
    }
}
</script>

<template>
    <ul>
        <li v-for="currentCard in card">
        {{ currentCard.name }}
        </li>
    </ul>
</template>

<style lang="scss">
</style>