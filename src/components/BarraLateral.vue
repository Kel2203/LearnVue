<template>
   <header>
    <h1>
        <img src="../assets/flower.png" alt="logo">
    </h1>
   </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'BarraLateral',
});
</script>

<style scoped>
header{
    background-color: #5c2fff;
    width: 100%;
    height: 100vh;
    padding: 1rem;
    
}

@media screen and (max-width: 768px){
    header{
        height: 2.5rem;
        height: auto;
    }
    
}
</style>