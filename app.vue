<template>
  <div>
    <div class="flex min-h-screen">
      <!-- Sidebar -->
      <div class="w-64 bg-sidebar border-r border-sidebar-border">
        <div class="p-4">
          <h1 class="text-xl font-bold">Admin Panel</h1>
        </div>
        <nav class="space-y-1 p-2">
          <NuxtLink to="/dashboard" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-sidebar-accent">
            <div class="i-lucide-layout-dashboard" />
            Dashboard
          </NuxtLink>
          <NuxtLink to="/connect" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-sidebar-accent">
            <div class="i-lucide-plug" />
            Connect Store
          </NuxtLink>
          <NuxtLink to="/products" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-sidebar-accent">
            <div class="i-lucide-package" />
            Products
          </NuxtLink>
          <NuxtLink to="/ai-agents" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-sidebar-accent">
            <div class="i-lucide-bot" />
            AI Agents
          </NuxtLink>
        </nav>
      </div>
      <!-- Main Content -->
      <div class="flex-1">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
