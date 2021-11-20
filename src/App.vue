<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>
  <div>
    <product-card
      v-for="product in products"
      :key="product.name"
      :product="product"
      @buy-now-clicked="buyNow"
      @add-to-cart-clicked="addToCart"
      @toggle-favourite="handleToggle"
    >
    </product-card>
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      products: [
        {
          name: "Apple iPhone 12 Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg",
          price: "৳161999",
          addedToFavourite: true
        },
        {
          name: "Walton Primo R8",
          thumbnail:
            "https://www.mobiledokan.com/wp-content/uploads/2021/05/Walton-Primo-R8-image.jpg",
          price: "৳10690",
          addedToFavourite: false
        },
        {
          name: "Oppo A15",
          thumbnail:
            "https://www.mobiledokan.com/wp-content/uploads/2021/01/Oppo-A15.jpg",
          price: "৳10990",
          addedToFavourite: true
        }
      ]
    };
  },
  methods: {
    buyNow(product) {
      console.log(product);
    },
    addToCart() {
      console.log("Adding...");
    },
    handleToggle(product) {
      product.addedToFavourite = !product.addedToFavourite;
    }
  },
  components: {
    ProductCard
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  margin-left: 22px;
}

body {
  font-family: sans-serif;
  line-height: 1.8;
}

header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
}

header h2 {
  text-align: center;
}

button {
  margin: 5px;
  padding: 5px 11px;
  cursor: pointer;
}
</style>
