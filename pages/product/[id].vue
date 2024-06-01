<template>
  <div class="flex flex-row bg bg-slate-100				">
    <div class="basis-1/2  ">
      <div class="grid  	">
        <div class="max-w-[360px] ml-28 mb-10 pt-20">
          <div class="grid  gap-3 ">
            <div>
              <img :src="product.thumb" :alt="product.imageAlt"
                   class="h-full w-full object-cover object-center group-hover:opacity-75"/>
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
<!--                                <div>{{product.description}}</div>-->
            </div>
          </div>
        </div>
      </div>

    </div>
    <div class="basis-1/2 pt-20  ">
      <div class="  text-black ">
        <h1 class="  text-xl dark:text-gray-400  ">პროდუქტის დასახელება</h1>
        <div>{{product.name}}</div>
      </div>

      <div class="flex ... pt-6">
        <div class="flex-none w-80 ... border-t">
        </div>
      </div>

      <div class="flex flex-nowrap gap-8 pt-12 text-black">
        <div><h1 class=" pl-3 mt-5 dark:text-gray-400 ">ფასი</h1>
          <div class=" pl-3 flex ...text-lg"> <p class="pr-2 text-blue-700 ">₾</p> {{product.price}}</div>

        </div>

        <div class="flex ... pt-8">
          <div class="flex-none  w-16	 ... border-r-2">
          </div>
        </div>

        <div><h2 class="mt-5 pl-3 text-black  dark:text-gray-400 ">რაოდენობა</h2>
          <div class="pl-9">{{product.stock}}</div></div>
      </div>
      <div class="flex ... pt-8">
        <div class="flex-none w-80 ... border-t">
        </div>

      </div>


      <div class="pt-12">
        <button type="button" class="py-2.5 px-5 me-2 mb-2 text-sm font-medium text-green-700 focus:outline-none bg-white rounded-full border border-gray-200 hover:bg-gray-100 hover:text-green-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700   dark:text-green-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-green-600">ყიდვა</button>
        <button type="button" class="py-2.5 px-5 me-2 mb-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-full border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700    dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700">კალათაში დამატება</button>

      </div>
    </div>
  </div>

</template>

<script setup lang="ts">



import axios from "axios";

const product = ref([])

const route = useRoute()

axios.get('http://localhost:8000/products/' + route.params.id)
    .then(response => {
      product.value = response?.data
    })

</script>

