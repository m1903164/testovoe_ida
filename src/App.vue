<template>
  <div class="app">
    <div class="app__container">
      <VHeader/>
      <div class="main">
        <div class="form-wrapper">
          <VForm/>
        </div>
        <VProductlist/>
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
            image: './assets/logo.png'
          },
          {
            id: 2,
            title: 'Наименование товара - 2',
            description: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
            price: 10000,
            image: './assets/logo.png'
          },
        ],
        title: '',
        description: '',
        price: '',
        image: '',
      }
    },
    methods: {
      addToList() {
        const newProduct = {
          id: Date.now(),
          title: this.title,
          description: this.description,
          price: this.price,
          image: this.image,
        }
        this.products.push(newProduct);
        this.title = '';
        this.description = '';
        this.price = '';
        this.image = '';
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
