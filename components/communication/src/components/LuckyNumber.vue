<template>
    <div>
        <h2>Generate Lucky Number</h2>
        <button @click="generateLuckyNumber" class="btn btn-primary">Generate</button>
        <p>Your lucky number is: {{ luckyNumber }}</p>
        <p v-if="luckyNumber ==0">Generate Lucky Number Range 1 to {{ maxNumber }}</p>
        <p v-else>click to generate lucky number</p>
        <span>Owner Name: {{ myname }}</span>
    </div>
</template>
<script setup>
import { ref ,inject} from 'vue';
const props= defineProps({
    maxNumber:{
        type:Number,
        default:100
    }
})
const myname=inject("myname");
let luckyNumber = ref(0);
function generateLuckyNumber() {
    luckyNumber.value = Math.floor(Math.random() * 100) + 1;
}
</script>