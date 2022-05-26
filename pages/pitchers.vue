<script setup>
const { data: pitchers } = await useAsyncData("pitchers", () =>
  queryContent("/pitchers").find()
);
</script>

<template>
  <main>
    <div class="flex flex-col items-center">
      <Card
        :data="p"
        v-for="p in pitchers"
        :key="p._id"
      ></Card>
    </div>
  </main>
</template>
