<template>
  <div class="hello">
        <b-card
          border-variant="dark"
          :header="nameProduct"
          align="center"
          style="height: 40rem"
        >
          <b-card-img :src="img"></b-card-img>
          <b-card-text> ราคา : {{ price }} </b-card-text>
          <label for="demo-sb">{{ textp }}</label>
          <b-form-spinbutton
            id="demo-sb"
            v-model="value"
            min="1"
            max="100"
          ></b-form-spinbutton>
          <b-button variant="outline-dark" class="mt-3">
            {{ textbutton }}</b-button>
        </b-card>
  </div>
</template>

<script>
export default {
  props: {
    img: String,
    price: Number,
    nameProduct: String
  },
  data() {
    return {
      value: 1,
      textbutton: "หยิบใส่ตะกร้า",
      textp: "จำนวน"
    };
  }
};
</script>
