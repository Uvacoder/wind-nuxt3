<script setup lang="ts">
const {
  params: { slug },
} = useRoute();

const { data: pitcher } = await useLazyAsyncData(`pitcher-${slug}`, () =>
  queryContent(`/pitchers/${slug}`).findOne()
);
</script>

<template>
  <div>
    <!--  <OverallStatus :report_data="log"></OverallStatus> -->
    <div
      class="mt-12 md:mt-20 font-semibold inline-flex flex-col md:flex-row md:items-end"
    ></div>

    <div class="flex flex-col items-center">
      <Card :data="pitcher"></Card>
    </div>
  </div>
</template>
