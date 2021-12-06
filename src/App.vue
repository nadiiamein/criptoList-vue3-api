<template>
  <div class="container">
    <h2 class="title">
      Cripto-Stoks-List App
    </h2>
      <TableStoks/>

  </div>
</template>

<script lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import {defineComponent}from 'vue'
import TableStoks from './components/TableStoks.vue'

export default defineComponent ({
  name: 'App',
  components: {
    TableStoks
  }
})
</script>




