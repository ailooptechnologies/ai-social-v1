<script setup lang="ts">
const name = ref('')
const email = ref('')
const password = ref('')

const handleRegister = () => {
  // Handle registration logic here
  console.log('Register attempt:', { 
    name: name.value,
    email: email.value,
    password: password.value 
  })
}
</script>

<template>
  <div class="min-h-screen flex items-center justify-center bg-background">
    <div class="w-full max-w-md p-8 bg-card rounded-lg shadow-lg">
      <div class="flex justify-center mb-8">
        <div class="i-lucide-user-plus text-4xl text-primary" />
      </div>
      
      <h1 class="text-2xl font-bold text-center mb-6">Create Account</h1>
      
      <form @submit.prevent="handleRegister" class="space-y-4">
        <div class="space-y-2">
          <label for="name" class="text-sm font-medium">Name</label>
          <input
            id="name"
            v-model="name"
            type="text"
            class="w-full p-2 rounded-md border bg-background"
            required
          />
        </div>

        <div class="space-y-2">
          <label for="email" class="text-sm font-medium">Email</label>
          <input
            id="email"
            v-model="email"
            type="email"
            class="w-full p-2 rounded-md border bg-background"
            required
          />
        </div>
        
        <div class="space-y-2">
          <label for="password" class="text-sm font-medium">Password</label>
          <input
            id="password"
            v-model="password"
            type="password"
            class="w-full p-2 rounded-md border bg-background"
            required
          />
        </div>
        
        <Button type="submit" class="w-full">Register</Button>
      </form>
      
      <p class="mt-4 text-center text-sm text-muted-foreground">
        Already have an account?
        <NuxtLink to="/auth/login" class="text-primary hover:underline">
          Sign In
        </NuxtLink>
      </p>
    </div>
  </div>
</template>