<template>
  <form class="flex" @submit.prevent="handleSubmit">
    <input v-model="title"   class="flex-1 mr-2 shadow border-0 rounded-full p-3 text-gray-700 text-base font-semibold outline-0" type="text" placeholder="List" />
    <button class="border-0 rounded-full text-slate-50 text-base font-bold uppercase w-20 bg-indigo-400 shadow cursor-pointer" type="submit" >
      add
    </button>
  </form>
</template>

<script setup lang="ts">
import { ref } from "vue"
import { ShoppingItem } from "@/types"

const props = defineProps<{ shoppingList: ShoppingItem[] }>()
const title = ref<string>()

const handleSubmit = () => {
  if (!title.value) return alert("No title provided!")
  props.shoppingList.push({ title: title.value, count: 0 })
  title.value = ""
}
</script>