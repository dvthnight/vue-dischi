<template>
    <main>
        <div class="container">
            <CardSpotify v-for="(card,i) in albumPerGenere" :key="i" :card="card"/>
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

        props: {
            genere: {
                type: String,
                
            },
            artista: {
                type: String,

            }
        },

        computed: {
            

            albumPerGenere: function(){
                return this.album.filter((el) => {
                    const {genre} = el;
                    return genre.toLowerCase().includes(this.genere.toLowerCase())
                })
            },

            albumPerArtista: function(){
                return this.album.filter((el) => {
                    const {author} = el;
                    return author.toLowerCase().includes(this.artista.toLowerCase())
                })
            },

            // albumFiltrati: function(){
                
            // },
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
        position: relative;

        .container{
            width: 1160px;
            // margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            
        }
    }
</style>