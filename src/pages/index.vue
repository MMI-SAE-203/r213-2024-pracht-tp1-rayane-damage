<script setup lang="ts">
import { ref } from 'vue';

//
const sectionOpen = ref(1)
</script>

<template>
  <h1 class="text-2xl">Bonjour monde !</h1>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 1" >bouton 1</button>
    <p v-show="sectionOpen==1?0:1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit, alias sint? Ex blanditiis quam voluptas aut error, rerum ducimus exercitationem provident nemo eum, laborum tempora debitis molestias nulla, voluptatum dolores.</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 2" >bouton 2</button>
    <p v-show="sectionOpen==2?0:2" >Quae illo facere tempore placeat! Exercitationem dolorem sint id placeat! Id porro eveniet saepe est neque. Quidem, at laborum? Eos cum dolor quidem temporibus voluptas nam ab perferendis maxime voluptatibus.</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 3" >bouton 3</button>
    <p v-show="sectionOpen==3?0:3" >Perspiciatis ducimus ex mollitia impedit architecto, aperiam dolore deserunt corrupti, velit veritatis earum ipsum tempora quae temporibus voluptatibus unde sint commodi totam rem alias sit voluptatem consectetur debitis? Recusandae, voluptatem?</p>
  </section>
</template>
