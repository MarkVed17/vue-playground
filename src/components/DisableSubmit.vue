<template>
    <div>
        <label>Enter a strong password</label>
        <input v-model="password" />
        <button :disabled="isDisabled">Submit</button>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const password = ref('')

const isDisabled = computed(() => {
  if (password.value.length < 8) {
    return true
  } else return false
})
</script>

<style>
</style>
