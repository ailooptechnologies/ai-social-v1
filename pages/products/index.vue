<script setup lang="ts">
interface Product {
  id: string
  name: string
  price: number
  currency: string
  category: string
  stock: number
}

const products = ref<Product[]>([
  {
    id: '1',
    name: 'Basic Tee',
    price: 29.99,
    currency: 'USD',
    category: 'Clothing',
    stock: 50
  },
  // Add more sample products as needed
])
</script>

<template>
  <div class="p-6 space-y-8">
    <div class="flex items-center justify-between">
      <h1 class="text-3xl font-bold">Products</h1>
      <Button>Add Product</Button>
    </div>

    <div class="bg-card rounded-lg shadow">
      <table class="w-full">
        <thead>
          <tr class="border-b">
            <th class="p-4 text-left">Name</th>
            <th class="p-4 text-left">Category</th>
            <th class="p-4 text-left">Price</th>
            <th class="p-4 text-left">Stock</th>
            <th class="p-4 text-left">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="product in products" :key="product.id" class="border-b">
            <td class="p-4">{{ product.name }}</td>
            <td class="p-4">{{ product.category }}</td>
            <td class="p-4">{{ product.currency }} {{ product.price }}</td>
            <td class="p-4">{{ product.stock }}</td>
            <td class="p-4">
              <Button variant="ghost" size="sm">Edit</Button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>