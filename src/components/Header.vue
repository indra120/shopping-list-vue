<template>
  <header
    class="flex justify-center items-center text-center bg-indigo-400 py-0 px-4 h-14"
  >
    <img :src="shoppingIcon" alt="shopping icon" class="size-6" />
    <h1 class="text-white text-2xl font-bold">Shopping List</h1>
  </header>
</template>

<script setup lang="ts">
import shoppingIcon from "../assets/shopping-icon.svg"
</script>
