<template>
  <div class="product-item column">
    <p class="product-title">{{ item.name }}</p>

    <img :src="item.imageUrl" :alt="item.name" />

    <span class="product-price">
      {{ item.price }}
    </span>

    <AddToCart @button-clicked="addToCart(item)" />
  </div>
</template>

<script>
import AddToCart from "./AddToCart";

export default {
  name: "ProductItem",
  components: {
    AddToCart,
  },
  props: {
    item: Object,
  },
  emits: ["add-to-cart"],
  data() {
    return {};
  },
  methods: {
    addToCart(item) {
      this.$emit("add-to-cart", item);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.column {
  width: 30%;
}

.product-item {
  box-shadow: rgba(0, 0, 0, 0.15) 0px 5px 15px 0px;
  cursor: pointer;
  background-color: #f6f6f6;
  border-radius: 1rem;
  position: relative;
  transition: all 0.2s ease;
}

.product-item::before {
  content: "<ProductItem />";
  position: absolute;
  top: -8%;
  left: 0;
  font-weight: bold;
  color: tomato;
}

.product-item:hover {
  transform: translateY(-10px);
}

.product-title {
  font-size: 1rem;
  font-weight: bold;
  color: tomato;
}

.product-price {
  font-size: 1.25rem;
  color: black;
  font-family: Verdana;
}

img {
  width: 100%;
}
</style>
