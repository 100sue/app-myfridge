<template>
    <a
      :href="href"
      target="_blank"
      class="px-6 py-2 font-bold rounded-xl border-1 text-white border-orange-600 bg-orange-500 transition-colors hover:bg-orange-700 hover:text-gray-400 "
    >
      <slot>YouTube</slot>
    </a>
  </template>
  
  <script setup>
  const props = defineProps({
    href: String
  })
  </script>
  