

<script setup>
import { Line } from 'vue-chartjs'
import {
  Chart as ChartJS,
  LineElement,
  PointElement,
  LinearScale,
  Title,
  Tooltip,
  Legend,
  CategoryScale,
} from 'chart.js'

ChartJS.register(
  LineElement,
  PointElement,
  LinearScale,
  Title,
  Tooltip,
  Legend,
  CategoryScale,
)

const chartData = ref({
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
  datasets: [
    {
      label: 'Dataset 1 (Левая ось)',
      data: [100, 200, 150, 300, 250, 400, 350],
      borderColor: 'rgb(255, 99, 132)',
      backgroundColor: 'rgba(255, 99, 132, 0.5)',
      yAxisID: 'y',
    },
    {
      label: 'Dataset 2 (Правая ось)',
      data: [10, 30, 50, 20, 60, 90, 70],
      borderColor: 'rgb(54, 162, 235)',
      backgroundColor: 'rgba(54, 162, 235, 0.5)',
      yAxisID: 'y',
      // yAxisID: 'y1',
    }
  ]
})

const chartOptions = {
  responsive: true,
  maintainAspectRatio: true, // чтобы размеры работали через CSS
  interaction: {
    mode: 'index',
    intersect: false,
  },
  stacked: false,
  plugins: {
    title: {
      display: true,
      text: 'Multi-Axis Line Chart',
    },
    legend: {
      position: 'top'
    }
  },
  scales: {
    y: {
      type: 'linear',
      display: true,
      position: 'left',
    },
    // y1: {
    //   type: 'linear',
    //   display: true,
    //   position: 'right',
    //   grid: {
    //     drawOnChartArea: false,
    //   }
    // }
  }
}

  const chartRef = ref(null)

  watch(chartData, () => {
    if (chartRef.value) {
      chartRef.value.chart.update()
    }
  }, { deep: true })

</script>

<template>
  <div>
    <div class="border-b">
      <p class="text-black/80 text-sm">Multi-Axis Line Chart</p>
    </div>
    <div class="h-full">
      <Line ref="chartRef" :data="chartData" :options="chartOptions" />
    </div>


    <div class="py-2">
      <p class="text-xs">{{ chartData.datasets[0].data }} {{ chartData.datasets[1].data }}</p>
    </div>


    <div class="grid grid-cols-3 gap-2">
      <input v-model="chartData.datasets[0].data[0]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[1]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="20">
      <input v-model="chartData.datasets[0].data[2]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="30">
      <input v-model="chartData.datasets[0].data[3]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[4]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[5]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[0].data[6]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
            
      <input v-model="chartData.datasets[1].data[0]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="20">
      <input v-model="chartData.datasets[1].data[1]" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="30">
      <input v-model="chartData.datasets[1].data[2]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[1].data[3]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[1].data[4]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[1].data[5]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
      <input v-model="chartData.datasets[1].data[6]" type="text" id="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm text-center rounded-md focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5  dark:bg-gray-700 dark:border-gray-700 dark:placeholder-gray-400 dark:text-gray-300 dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="10">
    </div>


  </div>
</template>

