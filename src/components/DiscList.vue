<template>
    <main>
        <section id="container-main">
            <div class="box-dischi">
                <!-- Stampo la lista dei dischi ottenuta tramite Axios -->
            </div>
        </section>
    </main>
</template>

<script>
export default {
  name: 'DiscList',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    main {
        width: 100%;
        height: 90vh;
        background-color: #1A253A;

        #container-main {
            width: 100%;
            height: 100%;

            .box-dischi {
                width: 100%;
                height: 100%;
            }
        }
    }
</style>