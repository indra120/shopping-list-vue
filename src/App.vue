<template>
  <Header />

  <section
    className="flex flex-col h-[540px] max-w-[480px] p-4 my-6 mx-auto bg-gray-100 rounded-xl shadow-md"
  >
    <AddShoppingItem :shopping-list="shoppingList" />
    <Info :shopping-list="shoppingList" @delete-all="deleteAllItems" />

    <ShoppingLists
      v-if="shoppingList.length > 0"
      :shopping-list="shoppingList"
    />
    <div
      v-else
      className="size-full flex justify-center items-center text-base font-semibold"
    >
      There is nothing in here...
    </div>
  </section>
</template>

<script setup lang="ts">
import { onMounted, onUpdated, ref } from "vue"
import { ShoppingItem } from "./types"
import Header from "./components/Header.vue"
import ShoppingLists from "./components/ShoppingLists.vue"
import AddShoppingItem from "./components/AddShoppingItem.vue"
import Info from "./components/Info.vue"

const shoppingList = ref<ShoppingItem[]>([])

onMounted(() => {
  const savedList = JSON.parse(localStorage.getItem("shopping-list")!) || []
  console.log(savedList)

  if (savedList.length > 0) {
    shoppingList.value = savedList
  }
})

onUpdated(() => {
  localStorage.setItem("shopping-list", JSON.stringify(shoppingList.value))
})

const deleteAllItems = () => {
  shoppingList.value = []
}
</script>
