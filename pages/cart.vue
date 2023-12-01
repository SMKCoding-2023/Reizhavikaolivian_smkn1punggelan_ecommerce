<template>
  <div class="container mx-auto my-8">
    <div v-if="cartItems.length === 0" class="text-center">
      <p>Your cart is empty</p>
    </div>
    <div v-else>
      <div v-for="product in cartItems" :key="product.id" class="mb-4">
        <div
          class="bg-white shadow-md p-4 rounded-md flex items-center justify-between"
        >
          <div class="flex items-center space-x-4">
            <img
              :src="product.image"
              alt="Product Image"
              class="h-16 w-16 object-cover rounded-md"
            />
            <div>
              <h3 class="text-lg font-semibold">{{ product.name }}</h3>
              <p class="text-gray-600">${{ product.price.toFixed(2) }}</p>
            </div>
          </div>

          <div v-if="product.discount">
            <p class="text-red-500">{{ product.discount }}% OFF</p>
          </div>

          <div class="flex items-center space-x-2">
            <button
              @click="decrementQuantity(product.id)"
              class="text-gray-500"
            >
              &minus;
            </button>
            <span class="text-lg">{{ product.quantity }}</span>
            <button
              @click="incrementQuantity(product.id)"
              class="text-gray-500"
            >
              &plus;
            </button>
          </div>

          <button @click="removeFromCart(product.id)" class="text-red-500">
            <i class="ri-delete-bin-7-fill text-lg"></i>
          </button>
        </div>
      </div>

      <div class="text-right mt-4">
        <p class="text-xl font-semibold">
          Total Price: ${{ calculateTotalPriceWithDiscount() }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const cartItems = ref([
  {
    id: 16,
    name: "gift box natal",
    price: 35,
    quantity: 1,
    discount: 10,
    image: "/images/product17.jpg",
  },
]);

const calculateTotalPriceWithDiscount = () => {
  return cartItems.value
    .reduce((total, product) => {
      const discountedPrice =
        (1 - product.discount / 100) * product.price * product.quantity;
      return total + discountedPrice;
    }, 0)
    .toFixed(2);
};

const removeFromCart = (id) => {
  cartItems.value = cartItems.value.filter((item) => item.id !== id);
};

const incrementQuantity = (id) => {
  const product = cartItems.value.find((item) => item.id === id);
  if (product) {
    product.quantity++;
  }
};

const decrementQuantity = (id) => {
  const product = cartItems.value.find((item) => item.id === id);
  if (product && product.quantity > 1) {
    product.quantity--;
  }
};
</script>

<style scoped></style>
