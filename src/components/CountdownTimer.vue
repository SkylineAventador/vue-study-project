<script setup>
import { ref, reactive } from "vue";
const props = defineProps({
  targetDate: String,
});
const countdownDate = ref(
  new Date(props.targetDate || "2023-12-31 23:59:59").getTime()
);
const isExpired = ref(false);
const isRunning = ref(false);
const timeData = reactive({ days: 0, hours: 0, minutes: 0, seconds: 0 });

const startCountdown = () => {
  const result = setInterval(() => {
    const now = new Date().getTime();
    const distance = countdownDate.value - now;

    timeData.days = ref(Math.floor(distance / (1000 * 60 * 60 * 24)));
    timeData.hours = ref(
      Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
    );
    timeData.minutes = ref(
      Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
    );
    timeData.seconds = ref(Math.floor((distance % (1000 * 60)) / 1000));

    if (distance < 0) {
      clearInterval(result);
      isExpired.value = true;
    }
  }, 1000);
};
</script>

<template>
  <div>
    <div>
      <label for="countdown-date-input">Enter date:</label>
      <input
        id="countdown-date-input"
        type="text"
        :value="props.targetDate"
        :disabled="props.targetDate"
        placeholder="Enter date"
      />
      <button
        class="uppercase"
        @click="
          () => {
            if (!isRunning) startCountdown();
          }
        "
      >
        Start countdown
      </button>
    </div>
    <h1 v-if="!isExpired" class="text-6xl font-semibold">
      {{
        `${timeData.days}d ${timeData.hours}h ${timeData.minutes}m ${timeData.seconds}s`
      }}
    </h1>
    <div v-else class="text-9xl">
      <span
        class="bg-gradient-to-r from-pink-500 to-purple-500 bg-clip-text font-extrabold text-transparent"
      >
        Hello world
      </span>
    </div>
  </div>
</template>
