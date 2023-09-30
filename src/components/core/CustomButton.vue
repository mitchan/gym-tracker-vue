<template>
  <button
    class="bg-green-700 py-2 px-4 rounded w-full mt-2 text-yellow-300"
    :disabled="disabled"
    :type="type ?? 'button'"
    :class="{ 'opacity-50': !!disabled }"
  >
    {{ label }}
  </button>
</template>

<script setup lang="ts">
defineProps<{
  label: string
  type?: 'button' | 'submit' | 'reset'
  disabled?: boolean
}>()
</script>
