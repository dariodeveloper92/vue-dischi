<template>
    <form  class="">
        <div class="search">
            <label for="type"> </label>
            <select name="type" id="type" v-model="selectText" @change="$emit('performSearch', selectText)">
                <option value=""> Scegli il tuo genere</option>
                <option> pop </option>
                <option> jazz </option>
                <option> metal </option>
            </select>
        </div>
    </form>
</template>

<script>
export default {
    name: 'Search',
    emits:['performSearch'],
    data() {
        return {
            selectText: '',
        }
    },
    methods: {

    }
}
</script>

<style>
    select {
        width: 200px;
        height: 50px; 
    }
</style>