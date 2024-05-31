<template>

  <div class="bg-white">
    <div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8">
      <h2 class="sr-only">Products</h2>

      <div class="grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 xl:gap-x-8">
        <a v-for="product in products" :key="product.id" :href="`product/${product.id}`" class="group">
          <div class="aspect-h-1 aspect-w-1 w-full overflow-hidden rounded-lg bg-gray-200 xl:aspect-h-8 xl:aspect-w-7">
<!--            <img :src="product.imageSrc" :alt="product.imageAlt"
                 class="h-full w-full object-cover object-center group-hover:opacity-75"/>-->
          </div>
          <h3 class="mt-4 text-sm text-gray-700">{{ product.name }}</h3>
          <p class="mt-1 text-lg font-medium text-gray-900">{{ product.price }}</p>
        </a>
      </div>
    </div>
  <UPagination v-model="page" :page-count="pagination?.total" :total="pagination?.total" :to="(page: number) => ({
      query: { page },
    })"/>
  </div>
</template>

<script setup>

import axios from "axios";

const products = ref([])
const page = ref(1)
const pagination = ref()
const route = useRoute()
const fetchData = () => {
  axios.get('http://localhost:8003/products?page=' + (route.query.page || 1), {
    params: {
      page: page.value
    }
  }).then(response => {
    console.log(response?.data?.data)
    products.value = response?.data?.data
    pagination.value = response?.data
  })
}

fetchData()

watch(() => route.query.page, fetchData)
const items = ref(Array(55))

</script>
