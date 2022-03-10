<template>
   <header>
       <figure class="logo">
           <img src="../assets/logo.svg" alt="">
       </figure>
   </header>
</template>

<script>

</script>


<style lang="scss" scoped>
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
    }
</style>