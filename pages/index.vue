<template>
  <Posts></Posts>
</template>

<script setup lang="ts">
  const { find } = useStrapi();
  const { data } = await useAsyncData("posts", function () {
    return find("posts", {
      populate: "*",
    });
  });
</script>

<style scoped></style>
