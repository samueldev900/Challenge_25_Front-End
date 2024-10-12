<script setup>
  import Formulario from './components/Formulario.vue';
  import Result from './components/Result.vue';
  import WaitResult from './components/WaitResult.vue';

</script>

<template>

  <main>

    <Formulario/>
    
  </main>


</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&display=swap');


*{
  padding: 0;
  margin: 0;
}
body{
  font-family: "Plus Jakarta Sans", sans-serif;
  font-optical-sizing: auto;
  background-color: hsl(0, 0%, 100%);
  padding-top: 20px;
}

:root {
  --cor1:hsl(202, 86%, 94%);
  --cor2:hsl(203, 41%, 72%);
  --cor3: hsl(200, 26%, 54%);
  --cor4:hsl(200, 24%, 40%);
  --cor5:hsl(202, 55%, 16%);
}
</style>