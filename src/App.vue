<template>
  <div id="app">
    <div>
      <b-navbar type="dark" variant="dark">
        <b-navbar-nav>
          <router-link to="/" class="container">
            <b-nav-item href="/">TuuShop</b-nav-item>
          </router-link>
        </b-navbar-nav>
        <b-navebar-nav class="ml-auto">
          <div>
            <router-link to="/About">
              <b-button variant="outline-info" @click="sum">
                <b-icon icon="basket" aria-hidden="ture"></b-icon>
              </b-button>
            </router-link>
          </div>
        </b-navebar-nav>
      </b-navbar>
    </div>
    <router-view
      :cardList="cardList"
      :product="product"
      @update-cart="UpProduct"
      :tprice="tprice"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      cardList: [
        {
          price: 20000,
          nameProduct: "รถถัง",
          img:
            "https://www.mrlhobby.com/wp-content/uploads/2020/09/tamiya-35055-m41-walker-wip-test-8.jpg"
        },
        {
          price: 10000,
          nameProduct: "เรือดำน้ำ",
          img:
            "https://kapitaennem0.files.wordpress.com/2017/05/c0151c5f0893b3bfeb4eda2deb3a7222.jpg?w=584"
        },
        {
          price: 25000,
          nameProduct: "เฮลิคอปเตอร์",
          img:
            "https://cdn.pixabay.com/photo/2021/01/24/21/58/helicopter-5946667__340.png"
        },
        {
          price: 9500,
          nameProduct: "โล่ตำรวจ",
          img:
            "https://www.grossiste-chinois-import.com/images/full_size/bouclier_police_POLBCLKL01.jpg"
        },
        {
          price: 2000,
          nameProduct: "กระบองตำรวจ",
          img: "https://www.newtv.co.th/images/content/ct_20190702111959469.jpg"
        },
        {
          price: 5000,
          nameProduct: "แก๊สน้ําตา",
          img: "https://www.catdumb.com/wp-content/uploads/2019/05/2-389.jpg"
        },
        {
          price: 200000,
          nameProduct: "M4A1",
          img:
            "https://cdn.shopify.com/s/files/1/0546/8541/products/TIPPMANN_M4_CARBINE_AIRSOFT_RIFLE1_clipped_rev_ROJ17E83UAKZ_2000x.png?v=1575931652"
        },
        {
          price: 2000,
          nameProduct: "รองเท้าคอมแบท",
          img: "https://dy.lnwfile.com/x7f4nw.jpg"
        }
      ],
      product: [],
      tprice: 0
    };
  },
  methods: {
    UpProduct(value) {
      this.product.push(value);
    },
    sum() {
      this.tprice = 0;
      for (var i = 0; i < this.product.length; i++) {
        this.tprice = this.tprice + this.product[i].Sum;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
