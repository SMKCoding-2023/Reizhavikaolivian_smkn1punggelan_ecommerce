<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps({
  product: {
    type: Object,
    default: {},
  },
});

const { baseStorageUrl } = useAppConfig();
const isAddedToCart = ref(false);

const addToCart = () => {
  console.log('Toggle Cart for product:', props.product);
  isAddedToCart.value = true;

  setTimeout(() => {
    isAddedToCart.value = false;
  }, 3000);
};
</script>

<template>
  <section class="bg-white shadow-xl rounded-xl overflow-hidden">
    <div :class="`w-full h-[200px] p-5 bg-gray-300`">
      <img :src="baseStorageUrl + props.product.image" class="w-full h-full object-contain"/>
    </div>
    <div class="px-5 pb-5 pt-9 relative">
      <NuxtLink :to="`/product/${props.product.id}`">
        <h3 class="text-lg font-bold mb-4 text-limit limit-2">{{ props.product.name }}</h3>
      </NuxtLink>
      <div class="flex justify-between items-center">
        <span class="text-sm font-normal">{{ props.product.category }}</span>
        <span class="text-sm font-normal">${{ props.product.price }}</span>
      </div>
      <div 
        :class="`cursor-pointer absolute -top-5 right-7 w-[50px] h-[50px]
        ${isAddedToCart ? 'bg-green-600 text-white' : (props.product.isCart ? 'bg-blue-600 text-white' : 'bg-white')} shadow-xl
        rounded-full flex justify-center items-center hover:bg-blue-600 hover:text-white
        transition duration-300`"
        @click="addToCart">
        <i class="ri-shopping-cart-2-line"></i>
      </div>

      
      <div v-if="isAddedToCart" class="bg-green-500 text-white p-2 rounded mt-2">
        Produk ditambahkan ke keranjang!
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>
