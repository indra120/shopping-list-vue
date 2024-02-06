<template>
  <section
    class="shadow overflow-x-hidden overflow-y-auto rounded-2xl max-h-[640px]"
  >
    <div
      class="flex justify-between items-center h-14 py-3 px-4 bg-white text-gray-700 text-base font-semibold"
      v-for="(item, i) in shoppingList"
      :key="i"
    >
      {{ item.title }}
    </div>
  </section>
</template>

<script setup lang="ts">
import { ShoppingItem } from "../types"

defineProps<{ shoppingList: ShoppingItem[] }>()
</script>
