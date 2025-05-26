<script setup lang="ts">
const email = ref('')
const password = ref('')

const handleLogin = () => {
  // Handle login logic here
  console.log('Login attempt:', { email: email.value, password: password.value })
}
</script>

<template>
  <div class="min-h-screen flex items-center justify-center bg-background">
    <div class="w-full max-w-md p-8 bg-card rounded-lg shadow-lg">
      <div class="flex justify-center mb-8">
        <div class="i-lucide-lock text-4xl text-primary" />
      </div>
      
      <h1 class="text-2xl font-bold text-center mb-6">Welcome Back</h1>
      
      <form @submit.prevent="handleLogin" class="space-y-4">
        <div class="space-y-2">
          <label for="email" class="text-sm font-medium">Email</label>
          <Input
            id="email"
            v-model="email"
            type="email"
            placeholder="Enter your email"
            required
          />
        </div>
        
        <div class="space-y-2">
          <label for="password" class="text-sm font-medium">Password</label>
          <Input
            id="password"
            v-model="password"
            type="password"
            placeholder="Enter your password"
            required
          />
        </div>
        
        <Button type="submit" class="w-full">Sign In</Button>
      </form>
      
      <p class="mt-4 text-center text-sm text-muted-foreground">
        Don't have an account?
        <NuxtLink to="/auth/register" class="text-primary hover:underline">
          Register
        </NuxtLink>
      </p>
    </div>
  </div>
</template>