<template>
    <form class="form-wrapper">
        <label>
            Enter Password
            <input type="password" v-model="passwords.passwordOne" />
        </label>
        <p>{{ passwords.passwordOne }}</p>
        <label>
            Re-enter Password
            <input type="password" v-model="passwords.passwordTwo" />
        </label>
        <p>{{ passwords.passwordTwo }}</p>
    </form>
    <h3>{{(passwords.passwordOne !== passwords.passwordTwo ? "Passwords don't match" : "")}}</h3>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const passwords = ref({
  passwordOne: '',
  passwordTwo: ''
})
</script>

<style>
.form-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: left;
}
</style>
