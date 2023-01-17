<template>
  <div style="display: flex; justify-content: center">
    <label>Enter a password: </label>
    <input :type="visibility" />
    <!-- <span
      v-if="visibility === 'text'"
      class="material-symbols-outlined"
      @click="toggleVisibility"
    >
      visibility
    </span> -->
    <span class="material-symbols-outlined" @click="toggleVisibility">
      {{ visibilityIcon }}
    </span>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const visibility = ref('password')

function toggleVisibility () {
  console.log(visibility.value)
  if (visibility.value === 'text') visibility.value = 'password'
  else visibility.value = 'text'
}

// Using computed property to change the visibility icon
const visibilityIcon = computed(() => {
  if (visibility.value === 'text') return 'visibility'
  else return 'visibility_off'
})
</script>

<style></style>
