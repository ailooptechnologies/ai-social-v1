<template>
  <div>
    <div class="flex min-h-screen">
      <!-- Sidebar -->
      <Sheet class="w-64 border-r bg-card">
        <div class="p-4 flex items-center gap-2">
          <div class="i-lucide-layout-dashboard text-2xl text-primary" />
          <h1 class="text-xl font-bold">
            Admin Panel
          </h1>
        </div>
        <ScrollArea class="h-[calc(100vh-4rem)]">
          <nav class="space-y-1 p-2">
          <NuxtLink to="/dashboard" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-layout-dashboard" />
            Dashboard
          </NuxtLink>
          <NuxtLink to="/connect" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-plug" />
            Connect Store
          </NuxtLink>
          <NuxtLink to="/products" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-package" />
            Products
          </NuxtLink>
          <NuxtLink to="/ai-agents" 
            class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-accent text-sm font-medium transition-colors"
            active-class="bg-accent text-accent-foreground">
            <div class="i-lucide-bot" />
            AI Agents
          </NuxtLink>
          <Separator class="my-4" />
          <div>
            <NuxtLink to="/auth/login"
              class="flex items-center gap-2 px-4 py-2 rounded-md hover:bg-accent text-sm font-medium transition-colors text-muted-foreground">
              <div class="i-lucide-log-out" />
              Logout
            </NuxtLink>
          </div>
          </nav>
        </ScrollArea>
      </Sheet>
      <!-- Main Content -->
      <div class="flex-1 overflow-auto">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
