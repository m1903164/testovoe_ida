<template>
  <div class="app">
    <div class="app__container">
      <VHeader/>
      <div class="main">
        <div class="form-wrapper">
          <VForm
            @create="createProduct"
          />
        </div>
        <VProductlist 
          :products="products"
        />
      </div>     
    </div>
  </div>
</template>

<script>
import VForm from "./components/v-form.vue";
import VProductlist from "./components/v-productlist.vue";
import VHeader from "./components/v-header.vue";


export default {
  name: 'App',
  components: {
    VForm,
    VProductlist,
    VHeader
},
  data() {
      return {
        products: [
          {
            id: 1,
            title: 'Наименование товара - 1',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 10000,
            image: 'https://i.imgur.com/w9uvR4T.png'
          },
          {
            id: 2,
            title: 'Наименование товара - 2',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 10000,
            image: 'https://i.imgur.com/w9uvR4T.png'
          },
          {
            id: 3,
            title: 'Наименование товара - 3',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 11000,
            image: 'https://i.imgur.com/w9uvR4T.png'
          },
          {
            id: 4,
            title: 'Наименование товара - 4',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 12000,
            image: 'https://i.imgur.com/w9uvR4T.png'
          },
          {
            id: 5,
            title: 'Наименование товара - 5',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 13000,
            image: 'https://i.imgur.com/w9uvR4T.png'
          },
        ],
      }
    },
    methods: {
      createProduct(product) {
        this.products.push(product);
      },
    }
}
</script>

<style lang="scss" scoped>
  @font-face {
    src: url("~@/assets/fonts/SourceSansPro-Regular.ttf");
    font-family: "Source Sans Pro";
    font-weight: 400;
  }
  @font-face {
    src: url("~@/assets/fonts/SourceSansPro-SemiBold.ttf");
    font-family: "Source Sans Pro";
    font-weight: 600;
  }
  @font-face {
    src: url("~@/assets/fonts/SourceSansPro-Bold.ttf");
    font-family: "Source Sans Pro";
    font-weight: 700;
  }
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: "Source Sans Pro", sans-serif;
  }
  .app__container {
    max-width: 1440px;
    width: 100%;
    margin: 0 auto;
    padding: 32px;
  }
  .main {
    display: grid;
    grid-template-columns: 1fr 3fr;
    gap: 16px;
    margin-top: 16px;
    @media (max-width: 1270px) {
      grid-template-columns: 1fr;
    } 
  }
  .form-wrapper {
    position: relative;
  }

</style>
