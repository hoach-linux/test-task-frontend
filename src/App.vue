<template>
  <div class="app">
    <div class="left-top-block top-block">
      <div class="products" v-for="items in onClickProductArr" :key="items.id">
        <p>{{ items }}</p>
      </div>
    </div>
    <div class="right-top-block top-block">{{ onClickProduct }}</div>
    <div class="left-bottom-block bottom-block">
      <div
        class="products"
        v-for="product in products"
        :key="product.id"
        @click="pushProductToArr"
      >
        <p>{{ product.name }}</p>
      </div>
    </div>
    <div class="right-bottom-block bottom-block">
      <div
        class="products"
        v-for="product2 in products2"
        :key="product2.id"
        @click="pushProduct"
      >
        <p>{{ product2.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    pushProductToArr(e) {
      if (this.onClickProductArr.length < this.maxItems) {
        this.onClickProductArr = [
          ...this.onClickProductArr,
          e.target.textContent,
        ];
      }
    },
    pushProduct(e) {
      this.onClickProduct = e.target.textContent;
    },
  },
  data() {
    return {
      maxItems: 6,
      onClickProductArr: "",
      onClickProduct: "",
      products: [
        {
          id: 1,
          name: "Shoes 1",
        },
        {
          id: 2,
          name: "Shoes 2",
        },
        {
          id: 3,
          name: "Shoes 3",
        },
        {
          id: 4,
          name: "Shoes 4",
        },
        {
          id: 5,
          name: "T-shirt 1",
        },
        {
          id: 6,
          name: "T-shirt 2",
        },
        {
          id: 7,
          name: "T-shirt 3",
        },
        {
          id: 8,
          name: "T-shirt 4",
        },
      ],
      products2: [
        {
          id: 11,
          name: "Jacket 1",
        },
        {
          id: 12,
          name: "Jacket 2",
        },
        {
          id: 13,
          name: "Jacket 3",
        },
        {
          id: 14,
          name: "Jacket 4",
        },
        {
          id: 15,
          name: "Hoodie 1",
        },
        {
          id: 16,
          name: "Hoodie 2",
        },
        {
          id: 17,
          name: "Hoodie 3",
        },
        {
          id: 18,
          name: "Hoodie 4",
        },
      ],
    };
  },
};
</script>

<style scoped>
body {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.app {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.right-top-block {
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.top-block,
.bottom-block {
  margin-top: 40px;
  display: flex;
  flex-wrap: wrap;
  min-width: 45vw;
  min-height: 45vh;
  border: 2px solid black;
}
.products {
  margin: 10px 0 0 10px;
  max-width: 60px;
  max-height: 60px;
  border: 2px solid black;
  cursor: pointer;
}
</style>
