<template>
  <div class="flex justify-between items-center w-full py-4 px-0">
    <div class="flex justify-center items-center text-gray-700 text-xs">
      <p class="font-bold">Total List: {{ shoppingList.length }}</p>
    </div>

    <div class="flex justify-center items-center text-gray-700 text-xs">
      <p class="font-bold">Total Counts: {{ totalCounts }}</p>
    </div>

    <button
      @click="emit('deleteAll')"
      class="bg-[none] border-0 p-0 text-red-500 text-xs font-bold cursor-pointer"
    >
      Delete All Items
    </button>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue"
import { ShoppingItem } from "../types"

const props = defineProps<{ shoppingList: ShoppingItem[] }>()
const emit = defineEmits<{ deleteAll: [] }>()

const totalCounts = computed(() => {
  return props.shoppingList.reduce((acc, curr) => acc + curr.count, 0)
})
</script>
