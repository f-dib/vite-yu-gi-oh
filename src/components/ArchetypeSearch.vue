<script>
export default {
    name: 'ArchetypeSearch',
}
</script>

<template>
    <form action="/action_page.php">
        <select @change="$emit('onchange')" name="archetype" id="archetype">
            <option value="Alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="Melodious">Melodious</option>
        </select>
    </form>
</template>

<style>

</style>