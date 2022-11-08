<script setup lang="ts">
import { useCounterStore } from '@/stores/counter';
import { storeToRefs } from "pinia";

const store = useCounterStore();

//const { name, doubleCount } = (store); //구조 분해 할당 - 반응형 x
const { name, doubleCount } = storeToRefs(store); //구조 분해 할당 - 반응형 o
const {count} = (store)

</script>
<template>
    <div class="about">
        <div>StoreView</div>
        {{ name }} : {{ doubleCount }} : {{count}}
        <button @click="store.increment">increment</button>
    </div>
</template>
  