<template>
    <div class="d-flex justify-content-center  vh-50">
        <div  class=" mt-5 p-20 bg-primary w-50" >
        <h2>Generate Lucky Number 2</h2>
        <input type="number" v-model="maxNumber" class=" form-control mb-3 w-25  d-flex justify-content-center" placeholder="Enter max number" />
        <button @click="generateLuckyNumber" class="btn btn-primary">Generate</button>
        <p>Your lucky number is: {{ luckyNumber }}</p>
        <p v-if="luckyNumber ==0">Generate Lucky Number Range 1 to {{ maxNumber }}</p>
        <p v-else>click to generate lucky number</p>
        
    </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';

let luckyNumber = ref(0);
function generateLuckyNumber() {
    luckyNumber.value = Math.floor(Math.random() * maxNumber.value) + 1;
}
const maxNumber = ref(100);
</script>
<style scoped></style>