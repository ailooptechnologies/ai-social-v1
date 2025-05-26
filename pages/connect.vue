<script setup lang="ts">
const platforms = [
  { name: 'Shopify', icon: 'i-lucide-shopping-bag', connected: false },
  { name: 'WooCommerce', icon: 'i-lucide-shopping-cart', connected: false },
  { name: 'Magento', icon: 'i-lucide-store', connected: false },
  { name: 'BigCommerce', icon: 'i-lucide-shopping-basket', connected: false },
  { name: 'Salla', icon: 'i-lucide-store', connected: false },
  { name: 'Wix', icon: 'i-lucide-globe', connected: false },
  { name: 'OpenCart', icon: 'i-lucide-shopping-cart', connected: false },
  { name: 'Drupal', icon: 'i-lucide-database', connected: false }
]
</script>

<template>
  <div class="p-6 space-y-8">
    <h1 class="text-3xl font-bold">Connect Your Store</h1>
    
    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
      <div v-for="platform in platforms" :key="platform.name" 
        class="p-6 bg-card rounded-lg shadow-sm hover:shadow transition-shadow">
        <div class="flex items-center gap-4">
          <div :class="[platform.icon, 'text-2xl']" />
          <div>
            <h3 class="font-semibold">{{ platform.name }}</h3>
            <p class="text-sm text-muted-foreground">
              {{ platform.connected ? 'Connected' : 'Not connected' }}
            </p>
          </div>
        </div>
        <Button class="mt-4 w-full" :variant="platform.connected ? 'outline' : 'default'">
          {{ platform.connected ? 'Disconnect' : 'Connect' }}
        </Button>
      </div>
    </div>
  </div>
</template>