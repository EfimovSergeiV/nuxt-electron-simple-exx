<script setup>
  import { Bar } from 'vue-chartjs'
  import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    BarElement,
    CategoryScale,
    LinearScale,
  } from 'chart.js'

  // Регистрируем модули Chart.js
  ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

  // Простые данные
  const chartData = ref({
    labels: ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'],
    datasets: [
      {
        label: 'Значения',
        backgroundColor: '#3b82f6',
        data: [10, 20, 15, 30, 25, 35, 40],
      }
    ]
  })

  const chartRef = ref(null)

  watch(chartData, () => {
    if (chartRef.value) {
      chartRef.value.chart.update()
    }
  }, { deep: true })

</script>


<template>
  <div class="">
    

    <div class="border-b">
      <p class="text-black/80 text-sm">Simple chart</p>
    </div>
    <div class="">
      <Bar ref="chartRef" :data="chartData" />      
    </div>

    <div class="py-2">
      <p class="text-xs">{{ chartData.datasets[0].data }}</p>
    </div>

    <div class="grid grid-cols-3 gap-2">
      <input v-model="chartData.datasets[0].data[0]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[1]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="20">
      <input v-model="chartData.datasets[0].data[2]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="30">
    
      <input v-model="chartData.datasets[0].data[3]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[4]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="20">
      <input v-model="chartData.datasets[0].data[5]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="30">

      <input v-model="chartData.datasets[0].data[6]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
    </div>

  </div>
</template>