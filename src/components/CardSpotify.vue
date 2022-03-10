<template>
   
    <div class="card">
        {{card.title}}
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
  
</style>