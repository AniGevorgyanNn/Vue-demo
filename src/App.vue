<script setup>

import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue'
let count = ref(0);
function plus(){
  count.value++;
}
function minus(){
  count.value--;
}
function plusTen(){
  count.value+=10;
}
function minusTen(){
  count.value-=10;
}
function reset(){
  count.value = 0;
}



</script>


<template>
 

  <main>
<h3> 

{{count}}
</h3>
<button @click="plus()">+1</button>
<button @click="plusTen()">+10</button>
<button @click="minus()">-1</button>
<button @click="minusTen()">-10</button>
<button @click="reset()"> reset</button>

    
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
