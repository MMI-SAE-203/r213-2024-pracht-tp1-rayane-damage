<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

const menuIsOpen = ref(false)
onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>


<template>
  <header>
    <button
      aria-controls="mainNav"
      aria-expanded="true"
      class="rounded-full border-2 border-red-600 bg-red-300 px-2"
      @pointerdown="menuIsOpen = !menuIsOpen"
    >
      menu
    </button>
    <Transition
      class="transition-transform duration-500"
      enter-from-class="-translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="-translate-x-full"
    >
      <nav id="mainNav" v-show="menuIsOpen">
        <ul>
          <li><a href="#"></a> item1</li>
          <li><a href="#"></a> item2</li>
          <li><a href="#"></a> item3</li>
        </ul>
      </nav>
    </Transition>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
