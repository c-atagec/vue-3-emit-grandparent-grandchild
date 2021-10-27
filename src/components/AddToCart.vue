<template>
  <button type="button" class="add-to-cart-button" @click="buttonClicked">
    Add To Cart
  </button>
</template>


<script>
export default {
  name: "AddToCart",
  methods: {
    buttonClicked() {
      this.$emit("button-clicked");
    },
  },
};
</script>

<style >
.add-to-cart-button {
  cursor: pointer;
  padding: 0.5rem;
  text-transform: uppercase;
  float: right;
  border: 1px solid transparent;
  background-color: #353839;
  color: #fff;
  transition: all 0.1s;
  border-bottom-right-radius: 1rem;
  position: relative;
}

.add-to-cart-button:hover {
  background-color: tomato;
}

.add-to-cart-button::before {
  content: "<AddToCart />";
  position: absolute;
  top: -24px;
  text-transform: capitalize;
  font-size: 0.9rem;
  left: 0;
  font-weight: bold;
  color: #000;
}
</style>