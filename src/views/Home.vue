<template>
  <div class="home">
    <b-container>
      <br />
      <b-row>
        <b-col cols="4" v-for="index in cardList" :key="index">
          <Product
            :img="index.img"
            :price="index.price"
            :nameProduct="index.nameProduct"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import Product from "@/components/product.vue";
export default {
  name: "Home",
  props: {
    cardList: Array,
  },
  components: {
    Product
  },
  data() {
    return {
      
    };
  },
  methods: {
    
  },
};
</script>
