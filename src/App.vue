<script setup></script>

<template>
  <div>
    <h1 class="text-6xl text-red-200">Hello Vue 3 with Tailwind css</h1>
    <div
      class="p-2 m-2 border-dashed border-2 border-indigo-600 grid grid-rows-5 grid-flow-col place-items-center gap-x-2 bg-violet-50"
    >
      <div
        v-for="n in 10"
        :key="n"
        class="border-solid border-2 bg-rose-200 text-rose-700 hover:text-white w-full hover:bg-rose-400 text-center text-lg font-semibold"
      >
        {{ n }}
      </div>
    </div>
  </div>
</template>
