<script setup>
  import InfoText01 from '../src/components/InfoText01.vue';

</script>

<template>

  <main class="p-5">
    <h1 class="text-3xl font-extrabold text-cor5">Mortage Calculator</h1>

    <p class="border-cor5 w-16 text-sm text-cor5 border-b my-5">Clear All</p>
    
    <InfoText01/>

  </main>


</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&display=swap');


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