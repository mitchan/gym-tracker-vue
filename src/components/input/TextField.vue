<template>
  <div class="flex flex-col mb-1">
    <label v-if="label" :for="id">{{ label }}</label>
    <input
      :id="id"
      :name="name"
      :type="type"
      :disabled="!!disabled"
      :placeholder="label"
      :value="modelValue"
      @input="handleInput($event)"
      class="border border-solid border-gray-400 rounded p-2 text-black"
    />
  </div>
</template>

<script setup lang="ts">
defineProps<{
  id: string
  name: string
  type?: 'text' | 'password'
  modelValue?: string
  label?: string
  disabled?: boolean
}>()

const emit = defineEmits(['update:modelValue'])

function handleInput(event: Event) {
  const target = event.target as HTMLInputElement
  emit('update:modelValue', target.value)
}
</script>
