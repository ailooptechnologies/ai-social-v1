<script setup lang="ts">
const agents = ref([
  {
    name: 'Customer Service Bot',
    description: 'Handles customer inquiries and support tickets',
    status: 'active'
  },
  {
    name: 'Product Recommender',
    description: 'Suggests products based on user preferences',
    status: 'inactive'
  },
  {
    name: 'Inventory Manager',
    description: 'Monitors stock levels and suggests reorders',
    status: 'active'
  }
])
</script>

<template>
  <div class="p-6 space-y-8">
    <div class="flex items-center justify-between">
      <h1 class="text-3xl font-bold">AI Agents</h1>
      <Button>Create Agent</Button>
    </div>

    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
      <div v-for="agent in agents" :key="agent.name" 
        class="p-6 bg-card rounded-lg shadow-sm">
        <div class="flex items-center justify-between mb-4">
          <h3 class="font-semibold">{{ agent.name }}</h3>
          <span :class="[
            'px-2 py-1 rounded-full text-xs',
            agent.status === 'active' ? 'bg-green-100 text-green-700' : 'bg-gray-100 text-gray-700'
          ]">
            {{ agent.status }}
          </span>
        </div>
        <p class="text-sm text-muted-foreground mb-4">{{ agent.description }}</p>
        <div class="flex gap-2">
          <Button variant="outline" size="sm">Configure</Button>
          <Button variant="ghost" size="sm">View Logs</Button>
        </div>
      </div>
    </div>
  </div>
</template>