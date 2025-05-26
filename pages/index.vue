<script setup lang="ts">
import { ref } from 'vue'

const stats = ref([
  { name: 'Total Revenue', value: '$45,231.89', change: '+20.1%' },
  { name: 'Orders', value: '2,345', change: '+15.1%' },
  { name: 'Customers', value: '12.5k', change: '+2.1%' },
  { name: 'Active Sessions', value: '573', change: '+10.3%' }
])
</script>

<template>
  <div class="p-6 space-y-8">
    <div class="flex items-center justify-between">
      <h1 class="text-3xl font-bold">Dashboard</h1>
      <Button>Download Report</Button>
    </div>

    <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4">
      <div v-for="stat in stats" :key="stat.name" class="p-4 bg-card rounded-lg shadow">
        <h3 class="text-sm text-muted-foreground">{{ stat.name }}</h3>
        <p class="text-2xl font-bold">{{ stat.value }}</p>
        <span :class="[
          'text-xs',
          stat.change.startsWith('+') ? 'text-green-500' : 'text-red-500'
        ]">{{ stat.change }}</span>
      </div>
    </div>
  </div>
</template>