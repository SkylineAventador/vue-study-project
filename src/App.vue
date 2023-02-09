<script setup>
import { ref } from "vue";
const colorArr = [
  { id: 1, color: "amber" },
  { id: 2, color: "violet" },
  { id: 3, color: "lime" },
  { id: 4, color: "rose" },
  { id: 5, color: "fuchsia" },
];
</script>

<template>
  <div>
    <h1 class="text-6xl text-red-200 dark:text-rose-100">
      Hello Vue 3 with Tailwind css
    </h1>
    <div
      class="m-2 grid auto-rows-auto grid-cols-5 place-items-center gap-x-5 gap-y-4 border-2 border-dashed border-indigo-600 bg-violet-50 p-2 dark:bg-slate-700"
    >
      <div
        v-for="item in colorArr"
        :key="item.id"
        class="w-full py-3 text-center"
      >
        <div
          v-for="n in 10"
          :key="n"
          :class="[
            'my-5',
            'rounded-md',
            'p-2',
            'text-xl',
            'font-semibold',
            `dark:bg-${item.color}-500`,
          ]"
        >
          {{ n + " - " + item.color }}
        </div>
      </div>
    </div>
  </div>
</template>
