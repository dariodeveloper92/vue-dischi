<template>
    <form  class="d-flex mb-5">
        <div class="search">
            <label for="type"> </label>
            <select name="type" id="type" v-model="selectText" @click.prevent="$emit('performSearch', selectText)">
                <option value=""> Scegli il tuo genere</option>
            </select>
        </div>
    </form>
</template>

<script>
export default {
    name: 'Search',
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