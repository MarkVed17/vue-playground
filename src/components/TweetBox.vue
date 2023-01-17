<template>
    <div>
        <textarea :class="textColor" style="height: 100px; width: 500px;" v-model="tweet"></textarea>
        <span>Characters count: </span>
        <span :class="textColor">{{ charCount }}</span>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const tweet = ref('')

const charCount = computed(() => {
  return 25 - tweet.value.length
})

const textColor = computed(() => {
  if (tweet.value.length > 20 && tweet.value.length < 25) {
    return 'warning'
  } else if (tweet.value.length > 25) {
    return 'limit-exceeded'
  }
  return 'default'
})
</script>

<style>
.default {
    color: black;
}

.warning {
    color: orange;
}

.limit-exceeded {
    color: red;
}
</style>
