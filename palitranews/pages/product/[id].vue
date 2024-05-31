<template>
  <div class="grid justify-center bg-stone-200">
    <div class="container-xl p-0 mt-5 gap-x-16 mb-11">
      <div class="grid">
        <div class="grid grid-column w-2/2 ">
          <div class="max-w-[660px] ml-12 mb-10">
            <div class="grid items-center gap-x-6 mt-5 mr-2">
              <div class="grid gap-4 ">
                <div>{{product.name}}</div>
                <div>{{product.description}}</div>
                <div>{{product.price}}</div>
                <div>{{product.stock}}</div>
                <div>
                  <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                </div>
                <div class="grid grid-cols-5 gap-4">
                  <div>
                    <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                  </div>
                  <div>
                    <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                  </div>
                  <div>
                    <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                  </div>
                  <div>
                    <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                  </div>
                  <div>
                    <img class="h-auto max-w-full rounded-lg" src="https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg" alt="">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script setup lang="ts">



import axios from "axios";

const product = ref([])

const route = useRoute()

axios.get('http://localhost:8003/products/' + route.params.id)
    .then(response => {
      product.value = response?.data
    })

</script>

