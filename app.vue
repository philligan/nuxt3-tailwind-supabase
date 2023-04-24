<script setup lang="ts">
const client = useSupabaseClient();

const { data: images } = await useAsyncData(
  "images",
  async () => client.from("images").select("*").order("created_at"),
  {
    transform: (result) => result.data,
  }
);

// client.from("images").insert({ src: "test", title: "test", author: "test" });
// client.from('images').delete().eq('title', 'Jennifur')
</script>

<template>
  <div>
    <CatImageGallery :images="images" />
  </div>
</template>