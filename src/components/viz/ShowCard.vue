<script setup lang="ts">
import { DateTime } from "luxon";
const props = defineProps({
  card: { type: Object as any, required: true },
});
</script>

<template>
  <div class="w-36">
    <p class="text-center">
      {{
        DateTime.fromFormat(card.date, "dd/MM/yy").toFormat("dd MMM").toString()
      }}
    </p>
    <img
      :src="`images/${card.number}.jpeg`"
      alt=""
      :class="`${card.rotate ? 'rotate-180' : ''}`"
    />
    <p class="text-center text-xs">{{ card.name }}</p>
  </div>
</template>

<style scoped></style>
