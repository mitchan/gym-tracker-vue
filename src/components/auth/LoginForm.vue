<template>
  <span class="text-3xl">asd</span>
  <form @submit.prevent="handleSubmit()">
    <TextField id="email" name="email" label="Email" v-model="local_email" />
    <TextField
      id="password"
      name="password"
      type="password"
      label="Password"
      v-model="local_password"
    />

    <button type="submit">Submit</button>
  </form>
</template>

<script setup lang="ts">
import { ref } from 'vue'

import type { LoginForm } from '@/types'

import TextField from '../input/TextField.vue'

const props = defineProps<Partial<LoginForm>>()

const local_email = ref(props.email ?? '')
const local_password = ref(props.password ?? '')

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
