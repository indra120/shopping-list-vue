<template>
  <Header />

  <section
    className="flex flex-col h-[540px] max-w-[480px] p-4 my-6 mx-auto bg-gray-100 rounded-xl shadow-md"
  >
    <AddShoppingItem :shopping-list="shoppingList" />
    <ShoppingLists :shopping-list="shoppingList" />
  </section>
</template>

<script setup lang="ts">
import { ref } from "vue"
import { ShoppingItem } from "./types"
import Header from "./components/Header.vue"
import ShoppingLists from "./components/ShoppingLists.vue"
import AddShoppingItem from "./components/AddShoppingItem.vue"

const shoppingList = ref<ShoppingItem[]>([
  { title: "Susu ultra", count: 1 },
  { title: "Tahu sumedang", count: 1 },
  { title: "Semangka", count: 1 },
])
</script>
