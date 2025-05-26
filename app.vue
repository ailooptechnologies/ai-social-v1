<template>
  <div>
    <div class="flex min-h-screen bg-background">
      <!-- Sidebar -->
      <div class="w-64 bg-card border-r border-border">
        <div class="p-4">
          <h1 class="text-xl font-bold flex items-center gap-2">
            <div class="i-lucide-layout-dashboard text-primary text-2xl" />
            Admin Panel
          </h1>
        </div>
        <nav class="space-y-0.5 p-2">
          <NuxtLink to="/dashboard" 
            class="flex items-center gap-2 px-4 py-2.5 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-layout-dashboard" />
            Dashboard
          </NuxtLink>
          <NuxtLink to="/connect" 
            class="flex items-center gap-2 px-4 py-2.5 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-plug" />
            Connect Store
          </NuxtLink>
          <NuxtLink to="/products" 
            class="flex items-center gap-2 px-4 py-2.5 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-package" />
            Products
          </NuxtLink>
          <NuxtLink to="/ai-agents" 
            class="flex items-center gap-2 px-4 py-2.5 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-bot" />
            AI Agents
          </NuxtLink>
          <div class="mt-4 pt-4 border-t border-border">
            <NuxtLink to="/auth/login"
              class="flex items-center gap-2 px-4 py-2.5 rounded-md hover:bg-accent text-sm font-medium transition-colors text-muted-foreground">
              <div class="i-lucide-log-out" />
              Logout
            </NuxtLink>
          </div>
        </nav>
      </div>
      <!-- Main Content -->
      <div class="flex-1 overflow-auto">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
