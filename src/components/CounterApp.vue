<template>
    <div>
        <h1 style="font-weight: 800">Simple Counter App</h1>
        <h1 style="color: dimgray;">{{ count }}</h1>
        <div style="display: flex; gap: 7px; justify-content: center;">
            <button @click="incrementCounter">Increment</button>
            <button @click="decrementCounter">Decrement</button>
            <button @click="incrementCounterBy5">Increment By 5</button>
            <button @click="decrementCounterBy5">Decrement By 5</button>
            <button @click="resetCounter">Reset</button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)

function incrementCounter () {
  count.value += 1
}

function decrementCounter () {
  count.value -= 1
}

function incrementCounterBy5 () {
  count.value += 5
}

function decrementCounterBy5 () {
  count.value -= 5
}

function resetCounter () {
  count.value = 0
}
</script>

<style scoped>

</style>
