<template>
  <section
    class="shadow overflow-x-hidden overflow-y-auto rounded-2xl max-h-[640px]"
  >
    <div
      class="flex justify-between items-center h-14 py-3 px-4 bg-white text-gray-700 text-base font-semibold"
      :class="shoppingList.length === i + 1 && 'border-b border-gray-100'"
      v-for="(item, i) in shoppingList"
      :key="i"
    >
      {{ item.title }}
      <div className="flex items-center justify-between w-32">
        <div
          className="flex justify-center items-center w-8 h-6 rounded text-indigo-500 bg-gray-100 shadow-md"
        >
          {{ item.count }}
        </div>

        <ActionButton
          @click="decrement(i)"
          :icon="minusIcon"
          alt="minus icon"
        />
        <ActionButton
          @click="shoppingList[i].count++"
          :icon="plusIcon"
          alt="plus icon"
        />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ShoppingItem } from "../types"
import ActionButton from "../components/ActionButton.vue"
import plusIcon from "../assets/plus-icon.svg"
import minusIcon from "../assets/minus-icon.svg"

const props = defineProps<{ shoppingList: ShoppingItem[] }>()

const decrement = (i: number) => {
  if (props.shoppingList[i].count > 0) {
    props.shoppingList[i].count--
  } else {
    props.shoppingList.splice(i, 1)
  }
}
</script>
