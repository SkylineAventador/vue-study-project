<script setup>
defineProps(["title", "msg"]);
const DEFAULT_TITLE = "Notification Title";
const DEFAULT_MSG =
  "Notification message. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ducimus esse praesentium similique sunt quidem nobis perspiciatis numquam beatae eligendi rerum.";
</script>
<template>
  <div
    class="mt-5 inline-block rounded-l-md border-l-2 border-l-slate-800 bg-slate-100 p-2 dark:border-l-slate-200 dark:bg-slate-700"
  >
    <h3 class="text-xl font-semibold dark:text-slate-200">
      {{ title || DEFAULT_TITLE }}
    </h3>
    <div class="text-lg">{{ msg || DEFAULT_MSG }}</div>
  </div>
</template>
