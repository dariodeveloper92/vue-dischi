<template>
    <header>
        <div id="container-header">
           <div class="logoSpotify">
               <a href="#">
                   <img alt="Spotify logo" src="../assets/spotify-logo.svg">
               </a>
            </div> 
        </div>
    </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    header {
        width: 100%;
        height: 10vh;

        #container-header {
            width: 100%;
            height: 100%;
            background-color: #49515f;

            .logoSpotify {
                width: 100%;
                height: 100%;
                
                a {
                    display: flex;
                    justify-content: flex-start;
                    align-items: center;
                }

                img {
                    width: 8%;
                }
            }
        }
    }
</style>