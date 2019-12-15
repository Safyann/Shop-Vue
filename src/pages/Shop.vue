<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section>
      <div class="container">
        <h1>shop Page</h1>
        <div class="item__wrapper">
          <ShopItem v-for="product in shopList" :key="product.id" :product="product" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import ShopItem from "../components/ShopItem";
export default {
  components: { ShopItem },
  data() {
    return {
      shopList: null
    };
  },
  created() {
    this.shopList = this.$store.getters.getShopList;

    console.log(this.shopList);
  }
};
</script>

<style lang="scss">
.item__wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
.item {
  max-width: 48%;
  text-align: center;
  font-size: 22px;
}
</style>
