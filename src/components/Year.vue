<script setup lang="ts">
defineProps<{
  years: number[]
}>()

const emit = defineEmits<{
  (e: 'updateYear', value: number): void
}>()
</script>

<template>
  <div class="flex flex-wrap">
    <div v-for="(year, key) in years" :key="key" class="w-1/2 px-0.5">
      <span class="flex rounded-md mt-1.5">
        <button
          type="button"
          class="px-3 py-2 block w-full leading-6 rounded-md bg-white text-xs 2xl:text-sm tracking-wide text-vtd-secondary-600 font-medium transition-colors border border-transparent hover:bg-vtd-secondary-100 hover:text-vtd-secondary-900 focus:bg-vtd-primary-50 focus:text-vtd-secondary-900 focus:border-vtd-primary-300 focus:ring-3 focus:ring-vtd-primary-500 focus:ring-opacity-10 focus:outline-hidden uppercase dark:bg-vtd-secondary-800 dark:hover:bg-vtd-secondary-700 dark:text-vtd-secondary-300 dark:hover:text-vtd-secondary-100 dark:focus:bg-vtd-secondary-700"
          @click="emit('updateYear', year)"
          v-text="year"
        />
      </span>
    </div>
  </div>
</template>
