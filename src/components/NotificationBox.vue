<script setup>
defineProps(["title", "msg"]);
const DEFAULT_TITLE = "Notification Title";
const DEFAULT_MSG =
  "Notification message. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ducimus esse praesentium similique sunt quidem nobis perspiciatis numquam beatae eligendi rerum.";
</script>
<template>
  <div
    class="mt-5 ml-5 inline-block max-w-xl rounded-md border-x-4 border-x-blue-400 bg-slate-100 p-2 text-justify"
  >
    <h3 class="text-xl font-semibold">
      {{ title || DEFAULT_TITLE }} -
      {{
        new Date().toLocaleString("cs-CZ", {
          day: "numeric",
          month: "long",
          year: "numeric",
          hour: "numeric",
          minute: "numeric",
        })
      }}
    </h3>
    <div class="indent-2 text-lg">{{ msg || DEFAULT_MSG }}</div>
  </div>
</template>
