<template>
  <h1>Products</h1>
  <div v-for="product in products" :key="product.id" class="products-listing">
    <h2>{{ product.name }}</h2>
    <h3>${{ product.price }}</h3>
    <button @click="addToCart(product)">Add to Cart</button>
  </div>
  <hr />
  <h1>Cart ({{ cartItems.length }})</h1>
  <div v-for="product in cartItems" :key="product.id" class="products-listing">
    <h2>{{ product.name }}</h2>
    <h3>${{ product.price }}</h3>
    <button @click="removeFromCart(product)">Remove</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

type Product = {
  id: number
  name: string
  price: number
}

type Cart = Product[]

const products: Array<Product> = [
  {
    id: 1,
    name: 'Eloquent JS',
    price: 1999
  },
  {
    id: 2,
    name: "You Don't Know JS!",
    price: 999
  },
  {
    id: 3,
    name: 'The Pragmatic Programmer',
    price: 2999
  }
]

const cartItems = ref<Cart>([])

function addToCart (product: Product) {
  const alreadyExists = cartItems.value.find(
    (currItem) => currItem.id === product.id
  )

  if (!alreadyExists) {
    cartItems.value.push(product)
  } else {
    alert(
      'Oops! Looks like the item already exists. Please add something else.'
    )
  }
}

function removeFromCart (product: Product) {
  cartItems.value = cartItems.value.filter(
    (currItem) => currItem.id !== product.id
  )
}
</script>

<style scoped>
.products-listing {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}
</style>
