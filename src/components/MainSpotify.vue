<template>
    <main>
        <div class="container">
            <CardSpotify v-for="(card,i) in album" :key="i" :card="card" />
        </div>
    </main>
    
</template>

<script>
    import CardSpotify from "./CardSpotify.vue"
    import axios from "axios"


    export default {
        components: {
            CardSpotify,
        },

        data(){
            return{
            album: []

            }
        },

        methods: {
            fetchAlbum: function(){
                axios.get("https://flynn.boolean.careers/exercises/api/array/music")
                .then(res => {
                    console.log(res.data.response);
                    this.album = res.data.response;
                })
                .catch(err => {
                    console.warn (err.response)
                })

            }
        },

        created(){
            this.fetchAlbum()
            
        }
    }
</script>


<style lang="scss" scoped>
    main{
        height: calc(100vh - 70px);
        width: 100%;
        background-color: rgb(29, 40, 51);
        color: white;
    }
</style>