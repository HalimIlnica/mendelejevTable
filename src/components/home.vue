<template>
  <v-container class="fill-height">
    <v-responsive class="fill-height">
      <!--
      <v-img height="300" src="@/assets/logo.svg" />
      <div class="text-body-2 font-weight-light mb-n1">Welcome to</div>
      <h1 class="text-h2 font-weight-bold">Vuetify</h1>
      -->

      <!-- <div class="py-14" /> -->
      <!-- {{selectedEl}} -->
      <v-row>
        <div class="square" :style="{ 'background-color': selectedEl && selectedEl.backgroundColor ? selectedEl.backgroundColor :'#8CED8C'}">
          <h2 class="numberElement">{{ selectedEl && selectedEl.atomicNumber ? selectedEl.atomicNumber : '1' }}</h2>
          <h1 class="symbolElement"><b>{{ selectedEl && selectedEl.symbol ? selectedEl.symbol : 'H' }}</b></h1>
          <h2 class="nameElement">{{ selectedEl && selectedEl.name ? selectedEl.name : 'Hidrogjen' }}</h2>
          <h5>{{ selectedEl && selectedEl.atomicWeight ? selectedEl.atomicWeight : '1.008' }}</h5>
        </div>
        <detailsPart class="detPart" :selectedEl="selectedEl"/>
      </v-row>
      <periodicTable class="periodicTab" @selectedElement="selectedElement" />
      <collapseButtons class="collButtons" />

    </v-responsive>
  </v-container>
</template>

<script setup>
// import infoSquare from '@/components/infoSquare.vue'
import detailsPart from '@/components/detailsPart.vue'
import periodicTable from '@/components/periodicTable.vue'
import collapseButtons from '@/components/collapseButtons.vue'

import { ref } from 'vue';

const selectedEl = ref({});
const selectedElement = (val) => {
  console.log('Selected element:', JSON.stringify(val));
  selectedEl.value = val;
  console.log('bora', selectedEl);
}
</script>

<style scoped>
.square {
  margin-top: 4%;
  margin-left: 3%;
  /* margin-right: 3%; */
}
.detPart {
  margin-bottom: 3%;
  margin-left: 3%;
  margin-right: 3%;
  /* float: right; */
}
.fill-height {
  background-color: aliceblue;
}
.periodicTab{
    margin-top: 3%;
}
/* .collButtons{
    margin-top: 3%;
} */
.square {
  width: 100px;
  height: 100px;
  /* background-color: hsl(120deg, 73%, 74%); */
  text-align: left;
  padding-top: 1%;
  padding-top: 1%;
  padding-left: 2%;
  padding-bottom: 5%;
  padding-right: 4%;
  box-sizing: content-box;
  overflow: hidden;
  border-radius: 10px;
}

.element-number,
.element-name,
.element-weight {
  margin: 0;
  max-width: 100%;
  overflow: hidden;
  white-space: nowrap;
  color: white;
}
.symbolElement,
.nameElement{
    font-family: 'Open Sans';
}
.numberElement{
    font-family: 'Open Sans';
    padding-top: 2%;
}
</style>


