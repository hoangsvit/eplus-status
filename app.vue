<script setup lang="ts">
const seriesData = ref([25, 39, 30, 15]);
const categories = ref(['Jun', 'Jul', 'Aug', 'Sept']);

const chartOptions = computed(() => ({
  chart: {
    type: 'line',
  },
  title: {
    text: 'Number of project stars',
  },
  xAxis: {
    categories: categories.value,
  },
  yAxis: {
    title: {
      text: 'Number of stars',
    },
  },
  series: [{
    name: 'New project stars',
    data: seriesData.value,
  }],
}));

// const onRender = () => {
//   console.log('Chart rendered');
// };

// return {
//   chartOptions,
//   onRender,
// };
</script>
<template>
  {{ chartOptions }}
  <client-only>
    <highchart :options="chartOptions" />
  </client-only>
</template>
