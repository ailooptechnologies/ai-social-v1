<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { Line } from 'vue-chartjs'
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
} from 'chart.js'

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
)

const stats = ref([
  { 
    name: 'Total Revenue',
    value: '$45,231.89',
    change: '+20.1%',
    icon: 'i-lucide-dollar-sign'
  },
  { 
    name: 'Orders',
    value: '2,345',
    change: '+15.1%',
    icon: 'i-lucide-shopping-cart'
  },
  { 
    name: 'Customers',
    value: '12.5k',
    change: '+2.1%',
    icon: 'i-lucide-users'
  },
  { 
    name: 'Active Sessions',
    value: '573',
    change: '+10.3%',
    icon: 'i-lucide-activity'
  }
])

const chartData = {
  labels: ['January', 'February', 'March', 'April', 'May', 'June'],
  datasets: [
    {
      label: 'Revenue',
      data: [30000, 35000, 32000, 40000, 38000, 45000],
      borderColor: 'rgb(var(--chart-1))',
      tension: 0.4
    },
    {
      label: 'Orders',
      data: [1500, 1800, 1600, 2100, 1900, 2300],
      borderColor: 'rgb(var(--chart-2))',
      tension: 0.4
    }
  ]
}

const chartOptions = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      position: 'top' as const
    }
  }
}
</script>

<template>
  <div class="p-6 space-y-8">
    <div class="flex items-center justify-between">
      <h1 class="text-3xl font-bold">Dashboard</h1>
      <Button>
        <div class="i-lucide-download" />
        Download Report
      </Button>
    </div>

    <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4">
      <div v-for="stat in stats" :key="stat.name" class="p-4 bg-card rounded-lg shadow">
        <div class="flex items-center gap-2 mb-2">
          <div :class="[stat.icon, 'text-xl text-primary']" />
          <h3 class="text-sm text-muted-foreground">{{ stat.name }}</h3>
        </div>
        <p class="text-2xl font-bold">{{ stat.value }}</p>
        <span :class="[
          'text-xs',
          stat.change.startsWith('+') ? 'text-green-500' : 'text-red-500'
        ]">{{ stat.change }}</span>
      </div>
    </div>
    
    <div class="grid gap-6 md:grid-cols-2">
      <div class="bg-card p-6 rounded-lg shadow">
        <h3 class="text-lg font-semibold mb-4">Revenue & Orders</h3>
        <div class="h-[300px]">
          <Line :data="chartData" :options="chartOptions" />
        </div>
      </div>
      
      <div class="bg-card p-6 rounded-lg shadow">
        <h3 class="text-lg font-semibold mb-4">Recent Activity</h3>
        <div class="space-y-4">
          <div v-for="i in 4" :key="i" class="flex items-center gap-3">
            <div class="i-lucide-circle text-primary" />
            <div>
              <p class="text-sm font-medium">New order #{{ 1000 + i }}</p>
              <p class="text-xs text-muted-foreground">{{ i }}h ago</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>