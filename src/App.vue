<script setup>
import { ref } from "vue";
const colorArr = ref([
  { id: 1, color: "red" },
  { id: 2, color: "green" },
  { id: 3, color: "blue" },
  { id: 4, color: "orange" },
  { id: 5, color: "purple" },
]);
</script>

<template>
  <div>
    <h1 class="text-center text-6xl font-extrabold text-violet-500">
      Vue 3 & Tailwind CSS - color shades exposition
    </h1>
    <div
      :class="`mb-2 grid auto-rows-auto grid-cols-5 place-items-center gap-x-5 gap-y-4 bg-gradient-to-b px-2 from-${colorArr[0].color}-500 via-${colorArr[2].color}-200 to-${colorArr[4].color}-700`"
    >
      <div
        v-for="item in colorArr"
        :key="item.id"
        class="w-full py-3 text-center"
      >
        <div
          v-for="n in 9"
          :key="n"
          :class="[
            `bg-${item.color}-${n * 100}`,
            'my-5',
            'rounded-md',
            'p-2',
            'text-xl',
            'font-semibold',
            `text-${item.color}-${n > 3 ? 100 : 900}`,
            'ring-2',
            `ring-${item.color}-200`,
          ]"
        >
          {{ n * 100 + " - " + item.color }}
        </div>
      </div>
    </div>
    <div class="px-2">
      <h3 class="mb-1 text-3xl text-slate-500">
        Try to enter your own values below:
      </h3>
      <div class="flex justify-between gap-2">
        <input
          type="text"
          placeholder="Try a new color"
          v-for="item in colorArr"
          :key="item.id"
          v-model="item.color"
          :class="`bg-${item.color}-100 text-${item.color}-900 w-full rounded-md py-1 px-2 text-lg font-semibold`"
        />
      </div>
    </div>
  </div>
</template>
