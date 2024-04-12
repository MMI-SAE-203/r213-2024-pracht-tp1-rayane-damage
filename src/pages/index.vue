<script setup lang="ts">
import { ref } from 'vue';
const sectionsData = [
  {
    label: 'bouton 1',
    texte: `texte panneau 1 Lorem ipsum dolor sit ame
    consectetur adipisicing elit. Inventore animi dolore,
    rerum magni laudantium quod excepturi laboriosam, 
    ex modi debitis harum reprehenderit eaque quam ut
    ea molestiae. Id, cum dolor!`
  },
  {
    label: 'bouton 2',
    texte: `texte panneau 2 Amet alias provident quos quis, 
    Officia ut ab dolores quos dolorem accusamus ad,
    consectetur unde minima, ipsum eligendi inventore id
    labore, laborum rerum laboriosam corrupti iste.
    Distinctio, perspiciatis!`
  },
  {
    label: 'bouton 3',
    texte: `texte panneau 3 Repudiandae corporis voluptates, 
    odit reprehenderit sint pariatur at voluptatum, cumque
    quia sit eligendi ex culpa eos, alias magnam molestiae
    id modi accusantium ipsa eveniet accusamus. Tempora 
    quis corporis et nam.`
  }
]
//
const sectionOpen = ref(0)
const sectionOpen2 = ref(0)
</script>

<template>
  <h1 class="text-2xl">Bonjour monde !</h1>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 1" >bouton 1</button>
    <p v-show="sectionOpen===1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit, alias sint? Ex blanditiis quam voluptas aut error, rerum ducimus exercitationem provident nemo eum, laborum tempora debitis molestias nulla, voluptatum dolores.</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 2" >bouton 2</button>
    <p v-show="sectionOpen===2" >Quae illo facere tempore placeat! Exercitationem dolorem sint id placeat! Id porro eveniet saepe est neque. Quidem, at laborum? Eos cum dolor quidem temporibus voluptas nam ab perferendis maxime voluptatibus.</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 3" >bouton 3</button>
    <p v-show="sectionOpen===3" >Perspiciatis ducimus ex mollitia impedit architecto, aperiam dolore deserunt corrupti, velit veritatis earum ipsum tempora quae temporibus voluptatibus unde sint commodi totam rem alias sit voluptatem consectetur debitis? Recusandae, voluptatem?</p>
  </section>

  <section v-for="({ label, texte }, key) of sectionsData" :v-key="key">
    <!-- <pre class="font-mono">key : {{ key }}</pre> -->
    <!-- <pre class="font-mono">label : {{ label }}</pre> -->
    <button class="font-mono" @pointerdown="sectionOpen2 = key">{{ label }}</button>
    <!-- <pre class="font-mono">texte : {{ texte }}</pre> -->
    <p class="font-mono" v-show="sectionOpen2===key" >{{ texte }}</p>
  </section>
</template>
