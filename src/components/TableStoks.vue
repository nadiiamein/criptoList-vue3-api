<template>
  <div class="list">
    <div class="list-item" v-for="value in stock" :key="value.stock">
      <div class="list-item__info">
        <div class="list-item__cover">
          <img :src="value.image" :alt="value.companyName">
        </div>
        <h3 class="list-item__title">
          {{value.companyName}}
          <span> {{value.symbol}}</span>
        </h3>
      </div>
      <span class="list-item__price"> {{value.price}} $</span>
    </div>
  </div>
  <h3>Info Co</h3>
  <select v-model="selected">
    <option value="" disabled="">Company</option>
        <option v-for="value in stock" :key="value.stock" :value="value.description"
        >{{value.companyName}}</option>

    </select>
    <div class="info">
      {{selected}}
    </div>
</template>


<script lang="ts">
import axios from 'axios'
 export default {
   name: 'List',
   data() {
     return {
       stock: [],
       errors: [],
       selected: ''
     }
   },
   created() {
     axios.get('https://financialmodelingprep.com/api/v3/profile/AAPL?apikey=3219a4e1770d01759828c8c27e779b26')
     .then(responce => {
       this.stock = responce.data
       console.log(responce)
     })
     .catch(e => {
       this.errors.push(e)
     })
   }
 }
</script>



