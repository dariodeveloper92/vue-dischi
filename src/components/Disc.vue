<template>
    <div class="disc text-center">
        <img class="img-fluid mb-3" :src="cover.poster" :alt="cover.name">
        <h2> {{ cover.title }} </h2>
        <h4> {{ cover.author }} </h4>
        <h5> {{ cover.year }} </h5>
    </div>
</template>

<script>
export default {
  name: 'Disc',
  props: ['cover']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .disc {
        width: 100%;
        height: 100%;

        img { 
            width: 100%;
            height: 100%;
        }
        h2 {
            color: white;
        }
        h4 {
            color: gray;
        }
        h5 {
            color: gray;
        }
    }
</style>