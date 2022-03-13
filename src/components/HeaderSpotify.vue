<template>
   <header>
       <figure class="logo">
           <img src="../assets/logo.svg" alt="">
       </figure>

       <div class="selection">
           <label for="genere" class="label">Genere</label>
            <select name="genere" id="genere" v-model="genere" @change="$emit('cerca', genere)">
                <!-- <option value="">Genere</option> -->
                <option v-for="(gen,i) in arrayGeneri" :key="i">{{gen}}</option>
                
            </select>

            <label for="artista" class="label">Artista</label>
            <select name="artista" id="artista" v-model="artista" @change="$emit('trovaArtista', artista)">
                <option v-for="(art, i) in arrayArtisti" :key="i">{{art}}</option>
                
            </select>

       </div>
   </header>
</template>

<script>

    export default{
        data(){
            return{
                genere:" ",

                arrayGeneri: ["Rock","Pop", "Jazz", "Metal"],

                arrayArtisti: ["Bon Jovi","Queen","Sting","Steve Gadd Band","Iron Maiden","Eric Clapton","Deep Purple","Metallica","Dave Weckl","Michael Jacjson"]
            }
        },

        // methods:{
        //     filtraGeneri: function(){
        //         console.log(this.genere);
        //     }
        // }
    }

</script>


<style lang="scss" scoped>
    .label{
        color: white;
        padding: 10px;
        text-transform: uppercase;
        font-weight: 700;

    }
    header{
        height: 70px;
        background-color: rgb(42, 51, 60);
        position: relative;

        figure{
            width: 100px;
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            left: 20px;
        }

        .selection{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }


    }
</style>