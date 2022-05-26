<template>
  <main>
    <ContentRenderer :value="data" />
  </main>
</template>

<script setup>
const { data } = await useAsyncData("pitchers", () =>
  queryContent("/pitchers").find()
);
console.log(data);
</script>
