<script>
import { store } from '../store.js';
export default {
    name: 'ArchetypeSearch',

    data(){
        return {
            store
        }
    }, 
}
</script>

<template>
    <form action="/action_page.php">
        <select @change="$emit('onchange')" name="archetype" id="archetype" v-model="store.searchArchetype">
            <option v-for="currentArchetype in store.allArchetype" :value="currentArchetype.archetype_name">{{ currentArchetype.archetype_name }}</option>
        </select>
    </form>
</template>

<style>

</style>