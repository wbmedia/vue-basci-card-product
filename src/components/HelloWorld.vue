<script setup>
import { ref, onMounted } from 'vue'
import greenSocksImg from './../assets/green_socks.jpg'
import blueSocksImg from './../assets/blue_socks.jpg'

defineProps({
  product: String,
})

const product_detail = ['50% Cotton', '20% Whool', '20% Polyester']
const variant_details = [
  { id: 2234, color: 'green', image: greenSocksImg },
  { id: 2235, color: 'blue', image: blueSocksImg },
]

const inventory = ref(100)
const inSale = ref(true)
const details = ref(product_detail)
const variants = ref(variant_details)
let image = ref(greenSocksImg)
let cart = ref(0)

function addToCart() {
  cart.value++
}

function updateImage(variantImage) {
  image.value = variantImage
}

onMounted(() => {
  console.log(`the initial cart count is ${cart.value}`)
})
</script>

<template>
  <h1>{{ product }}</h1>
  <img class="image" :src="image" alt="green socks image" />
  <h2 v-if="inSale">In Sale!</h2>
  <p v-if="inventory > 10">In Stock</p>
  <p v-else-if="inventory <= 10 && inventory > 0">Almost sold out!!</p>
  <p v-else>Out of Stock</p>

  <div class="cart shadow-lg">
    <p>
      Cart: <strong>{{ cart }}</strong>
    </p>
  </div>
  <div>
    <ul>
      <li v-for="detail in details" :key="detail">
        {{ detail }}
      </li>
    </ul>
  </div>
  <div
    v-for="variante in variants"
    :key="variante.id"
    @mouseover="updateImage(variante.image)"
  >
    {{ variante.color }}
  </div>
  <button
    @click="addToCart"
    class="btn bg-green-400 text-white hover:bg-green-500"
  >
    Add to Cart
  </button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.image {
  width: 300px;
  max-width: 100%;
  display: block;
}
.cart {
  display: flex;
  position: absolute;
  top: 100px;
  right: 10px;
  background-color: black;
  justify-content: center;
  padding: 5px;
  width: 100px;
}

.cart > p {
  text-align: center;
  color: white;
}
</style>
