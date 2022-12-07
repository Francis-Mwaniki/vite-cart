<template>
  <main class="min-h-screen bg-slate-700">
    <!-- Cart -->
    <div class="py-2">
      <button
        v-on:click="showCart"
        class="md:px-5 px-20 pt-1 py-3 md:py-2 flex justify-center items-center mx-auto text-white rounded bg-slate-900"
      >
        {{ showed ? "close cart" : "view cart" }}
      </button>
    </div>
    <div v-if="showed">
      <div v-show="showed">
        <Maincart :cartStore="cartStore" />
      </div>
    </div>
    <div v-else>
      <h1
        class="px-1 mx-auto justify-center items-center pb-2 flex uppercase text-2xl text-white py-2"
      >
        products
      </h1>

      <div
        class="max-w-lg md:max-w-4xl rounded p-1 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 grid-flow-row gap-3 justify-center items-center mx-auto md:flex-nowrap flex-wrap"
      >
        <div
          v-for="product in products"
          :key="product"
          class="rounded border p-3 border-gray-800 bg-slate-800 flex flex-col gap-y-2 md:max-w-lg"
        >
          <span
            ><img
              src="../assets/imgs/fb.jpg"
              class="object-cover w-full h-40 rounded"
          /></span>
          <h3 class="text-white flex justify-center items-center mx-auto">
            {{ product.name }}
          </h3>

          <div class="text-white flex justify-center items-center mx-auto">
            Ksh.{{ product.cost }}
          </div>
          <button
            v-on:click="addItemToCart(product)"
            class="md:px-5 px-20 py-3 md:py-2 flex justify-center items-center mx-auto hover:bg-white hover:text-black text-white rounded bg-slate-900"
          >
            add
          </button>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
import Maincart from "../components/Maincart.vue";
export default {
  name: "app",
  data() {
    return {
      cartStore: [],
      showed: false,
      products: [
        {
          id: 1,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 2,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 3,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 4,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 1,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 2,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 3,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 4,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 1,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 2,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 3,
          name: "cosmas",
          cost: "500",
        },
        {
          id: 4,
          name: "cosmas",
          cost: "500",
        },
      ],
    };
  },
  methods: {
    addItemToCart(product) {
      this.cartStore.push(product);
      console.log(this.cartStore);
    },
    showCart() {
      this.showed = !this.showed;
    },
  },

  components: { Maincart },
};
</script>

<style></style>
