<template>
   
    <div class="card">
        <figure>
            <img :src="card.poster" alt="">
        </figure>
        <h3>{{card.title}}</h3>
        <h4> {{card.author}} </h4>
        <div class="year">{{card.year}}</div>
    </div>

    
</template>

<script>

    export default{
       props:{
           card:{
               type: Object,
               require: true,
           }
       }

       
    }
</script>


<style lang="scss" scoped>
    .card{
        width: 200px;
        background-color: rgb(42, 51, 60);
        padding: 20px;

        figure{
            width: 160px;
            margin: 0 auto;
        }

        h3{
            font-size: 22px;
            text-transform: uppercase;
            padding: 10px;
        }

        h4{
            font-size: 20px;
            font-weight: 500;
            color: rgb(112, 112, 112);
            // padding: 10px;
        }

        .year{
            font-weight: 500;
            color: rgb(112, 112, 112);
        }
    }
</style>