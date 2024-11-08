<script setup lang="ts">
import QuizCard from '@/components/QuizCard.vue';


</script>

<template>
  <div class="container">
    <QuizCard />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');

*{
  box-sizing: border-box;
}


.container {
  background: #fffbd5;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #b20a2c, #fffbd5);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #b20a2c, #fffbd5); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
