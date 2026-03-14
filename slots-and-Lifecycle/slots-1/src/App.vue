

<template>
<div class="d-flex justify-content-center ">
    <button @click="changeVersion" class="btn btn-primary m-2"> version 1</button>
<button @click="changeVersion" class="btn btn-primary m-2"> version 2</button>
</div>
<keep-alive>
    <component :is="luckynumber" />
</keep-alive>
</template>

<script setup>
import LuckyNumberV1 from './components/LuckyNumberV1.vue';
import LuckyNumberV2 from './components/LuckyNumberV2.vue';
import { ref , computed} from 'vue';
const isLuckyNumberV1 = ref(true);

const luckynumber = computed(() => (isLuckyNumberV1.value ? LuckyNumberV1 : LuckyNumberV2));
function changeVersion() {
    isLuckyNumberV1.value = !isLuckyNumberV1.value;
}
</script>

<style scoped></style>
