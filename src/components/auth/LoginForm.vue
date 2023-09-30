<script setup lang="ts">
import { ref } from 'vue'

import type { LoginForm } from '@/types'

import CustomButton from '../core/CustomButton.vue'
import TextField from '../input/TextField.vue'

defineProps<{
  register?: boolean
}>()

const local_email = ref('')
const local_password = ref('')

const emit = defineEmits<{
  (e: 'form-submit', value: LoginForm): void
}>()

function handleSubmit() {
  emit('form-submit', {
    email: local_email.value,
    password: local_password.value
  })
}
</script>

<template>
  <form @submit.prevent="handleSubmit()" class="px-5 w-full">
    <TextField id="email" name="email" label="Email" v-model="local_email" />

    <TextField
      id="password"
      name="password"
      type="password"
      label="Password"
      v-model="local_password"
    />

    <CustomButton :label="register ? 'Registrati' : 'Login'" type="submit" />
  </form>
</template>
