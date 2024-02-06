<template>
  <button class="border-0 bg-[unset] p-[unset] size-6 cursor-pointer">
    <img :src="icon" :alt="alt" />
  </button>
</template>

<script setup lang="ts">
defineProps<{ icon: string; alt: string }>()
</script>
