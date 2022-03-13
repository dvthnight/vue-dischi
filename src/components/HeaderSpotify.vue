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

            <!-- <label for="artista" class="label">Artista</label>
            <select name="artista" id="artista" v-model="artista">
                <option value="">Artista</option>
                <option value="Bon_Jovi">Bon Jovi</option>
                <option value="Queen">Queen</option>
                <option value="Sting">Sting</option>
                <option value="Steve_Gadd">Steve Gadd Band</option>
                <option value="Iron_Maiden">Iron Maiden</option>
                <option value="Eric_Clapton">Eric Clapton</option>
                <option value="Deep_Purple">Deep Purple</option>
                <option value="Metallica">Metallica</option>
                <option value="Dave_Weckl">Dave Weckl</option>
                <option value="Michael_Jacjson">Michael Jacjson</option>
            </select> -->

       </div>
   </header>
</template>

<script>

    export default{
        data(){
            return{
                genere:" ",

                arrayGeneri: ["Rock","Pop", "Jazz", "Metal"]
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