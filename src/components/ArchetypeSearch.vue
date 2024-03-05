<script>
import { store } from '../store.js';
export default {
    name: 'ArchetypeSearch',

    data(){
        return {
            store
        }
    }
}
</script>

<template>
    <form action="/action_page.php">
        <select @change="$emit('onchange')" name="archetype" id="archetype" v-model="store.searchArchetype">
            <option value="Alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="Melodious">Melodious</option>
        </select>
    </form>
</template>

<style>

</style>