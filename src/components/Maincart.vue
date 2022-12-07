<template>
  <main>
    <h1
      class="px-1 mx-auto justify-center items-center pb-2 flex uppercase text-xl text-white py-2"
    >
      Items({{ cartStore.length }})
    </h1>
    <div
      class="max-w-lg md:max-w-4xl overflow-x-auto text-white rounded p-1 flex-row flex gap-3 justify-center items-center mx-auto md:flex-nowrap"
      v-if="cartStore.length != 0"
    >
      <div
        v-for="product in cartStore"
        :key="product"
        class="rounded border p-3 border-gray-800 bg-slate-800 flex flex-col gap-y-2 md:max-w-sm"
      >
        <span
          ><img
            src="../assets/imgs/fb.jpg"
            class="object-cover w-full md:h-16 h-10 rounded"
        /></span>
        <h3 class="text-white flex justify-center items-center mx-auto">
          {{ product.name }}
        </h3>

        <div class="text-white flex justify-center items-center mx-auto">
          Ksh.{{ product.cost }}
        </div>
        <button
          v-on:click="removeItemFromCart(product)"
          class="md:px-5 px-20 py-3 md:py-2 flex justify-center items-center mx-auto hover:bg-white hover:text-black text-white rounded bg-slate-900"
        >
          remove
        </button>
      </div>
    </div>
    <div
      class="py-3 justify-center items-center flex mx-auto text-white"
      v-else
    >
      Your cart is currently empty!! Add some products!
    </div>
  </main>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Maincart",
  props: ["cartStore"],
  data() {
    return {
      items: "",
    };
  },
  methods: {
    removeItemFromCart(product) {
      // eslint-disable-next-line vue/no-mutating-props
      this.cartStore.splice(this.cartStore.indexOf(product));
    },
  },
};
</script>

<style></style>
