<template>
    <div class="disc text-center">
        <div class="cardDisc">
            <img class="img-fluid mb-3" :src="cover.poster" :alt="cover.name">
            <h2> {{ cover.title }} </h2>
            <h4> {{ cover.author }} </h4>
            <h5> {{ cover.year }} </h5>
        </div>
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
        position: relative;
        display: flex;
        
        .cardDisc {
            background-color: #49515f;
            width: 200px;
            height: 250px;
            position: relative;
            padding: 15px 10px;
            
            img { 
                width: 100px;
                object-fit: contain;
                vertical-align: middle;
            }
            h2 {
                color: white;
                font-size: 20px;
            }
            h4 {
                color: white;
                font-size: 15px;
            }
            h5 {
                color: white;
                font-size: 12px;
            }
        }
    }
</style>