<script setup lang="ts">
const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="flex flex-wrap w-1/3">
    <div class="w-full p-1 md:p-2">
      <nuxt-img
        :src="src"
        :alt="alt"
        class="block object-cover object-center w-full h-hull rounded-lg"
        format="webp"
      />
    </div>
  </div>
</template>