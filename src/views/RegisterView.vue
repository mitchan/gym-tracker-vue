<script setup lang="ts">
import LoginForm from '@/components/auth/LoginForm.vue'
import type { LoginForm as LoginFormType } from '@/types'

function handleFormSubmit(data: LoginFormType) {
  console.log(data)
}
</script>

<template>
  <LoginForm @form-submit="handleFormSubmit($event)" />
</template>
