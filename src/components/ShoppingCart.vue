<script setup>
import { ref, onMounted } from 'vue'

import pumaBlue from './../assets/puma_blue.jpg'
import pumaGreen from './../assets/puma_green.jpg'
import pumaRed from './../assets/puma_red.jpg'
import pumaYellow from './../assets/puma_yellow.png'

defineProps({
  product: String,
})

const variant_details = [
  {
    id: 2234,
    color: 'bg-green-500',
    image: pumaGreen,
  },
  {
    id: 2235,
    color: 'bg-blue-900',
    image: pumaBlue,
  },
  {
    id: 2236,
    color: 'bg-red-500',
    image: pumaRed,
  },
  {
    id: 2237,
    color: 'bg-yellow-500',
    image: pumaYellow,
  },
]

const variants = ref(variant_details)
let cart = ref(0)
let tenisImage = ref(pumaGreen)
const price = ref(89.99)
const oldPrice = ref(129.99)

function addToCart() {
  cart.value++
}

function clearCart() {
  cart.value = 0
}

function updateImage(variantImage) {
  tenisImage.value = variantImage
}

onMounted(() => {
  console.log(`the initial cart count is ${cart.value}`)
})
</script>

<template>
  <div
    class="relative m-10 flex w-full max-w-xs flex-col overflow-hidden rounded-lg border border-gray-100 bg-white shadow-md"
  >
    <a class="relative mx-3 mt-3 flex h-60 overflow-hidden rounded-xl" href="#">
      <img class="object-cover" :src="tenisImage" alt="product image" />
      <span
        class="absolute top-0 left-0 m-2 rounded-full bg-black px-2 text-center text-sm font-medium text-white"
        >39% OFF</span
      >
    </a>
    <div class="mt-4 px-5 pb-5">
      <a href="#">
        <h5 class="text-xl tracking-tight text-slate-900">
          Puma Classic Shoes
        </h5>
      </a>
      <div>
        <ul class="flex flex-row justify-center items-center">
          <li
            class="mr-4 last:mr-0"
            v-for="variante in variants"
            :key="variante.id"
            @mouseover="updateImage(variante.image)"
          >
            <span
              class="block p-1 border-2 border-gray-500 rounded-full transition ease-in duration-300"
            >
              <a
                href="#blue"
                :class="variante.color"
                class="block w-6 h-6 rounded-full"
                target="_blank"
              >
              </a>
            </span>
          </li>
        </ul>
      </div>
      <div class="mt-2 mb-5 flex items-center justify-between">
        <p>
          <span class="text-3xl font-bold text-slate-900">${{ price }}</span>
          <span class="text-sm text-slate-900 line-through"
            >${{ oldPrice }}</span
          >
        </p>

        <div class="flex items-center">
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-yellow-300"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            ></path>
          </svg>
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-yellow-300"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            ></path>
          </svg>
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-yellow-300"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            ></path>
          </svg>
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-yellow-300"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            ></path>
          </svg>
          <svg
            aria-hidden="true"
            class="h-5 w-5 text-yellow-300"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            ></path>
          </svg>
          <span
            class="mr-2 ml-3 rounded bg-yellow-200 px-2.5 py-0.5 text-xs font-semibold"
            >5.0</span
          >
        </div>
      </div>
      <a
        href="#"
        @click="addToCart"
        class="flex items-center justify-center rounded-md bg-slate-900 px-5 py-2.5 text-center text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-blue-300"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="mr-2 h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"
          />
        </svg>
        Add to cart &nbsp; ({{ cart }})</a
      >
      <a
        href="#"
        @click="clearCart"
        class="flex mt-1 items-center justify-center rounded-md bg-slate-500 px-5 py-2.5 text-center text-sm font-medium text-white hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-blue-300"
      >
        Clear Cart
      </a>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.image {
  width: 100%;
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
