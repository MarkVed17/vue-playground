<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <!-- <CounterApp /> -->
    <PasswordMatcher />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
// import CounterApp from '@/components/CounterApp.vue'
import PasswordMatcher from '@/components/PasswordMatcher.vue'

export default defineComponent({
  name: 'HomeView',
  components: {
    // HelloWorld,
    // CounterApp,
    PasswordMatcher
  }
})
</script>
