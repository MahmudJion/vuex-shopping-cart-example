<template>
  <div>
    <navbar></navbar>
    <products></products>
    <cart></cart>
    <toast
      :show="toast.show"
      :text="toast.text"
      @hide-toast="hideToast"
    ></toast>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Products from "./components/Products.vue";
import Cart from "./components/Cart.vue";
import Toast from "./components/Toast.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Products,
    Cart,
    Toast,
  },
  data() {
    return {};
  },
  computed: {
    toast() {
      return this.$store.getters.toast;
    },
  },
  methods: {
    hideToast() {
      this.$store.commit("hideToast");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
