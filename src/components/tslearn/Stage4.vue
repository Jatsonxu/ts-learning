<template>

</template>

<script setup lang="ts">
import {useCounterStore} from "@/stores/counter";

const CounterStore = useCounterStore()
console.log(CounterStore.count)
</script>
