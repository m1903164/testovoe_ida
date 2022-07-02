<template>
          <div class="prod-list">
            <div class="product" v-for="product in products" v-bind:key="product.id">
                <img class="product__image" src='{{product.image}}'>
                <div class="product__text">
                    <h3 class="product__title">{{ product.title }}</h3>
                    <p class="Product__description">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
                    <h2 class="product__price">{{ product.price }} руб.</h2>
                </div>
            </div>
          </div>
</template>

<script>
export default {
    name: 'VproductList'
}
</script>

<style lang="scss" scoped>
    .prod-list {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 16px;
        position: relative;
        min-height: 100px;
    }

    .product {
        background: #FFFEFB;
        box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        position: relative;
        &__image {
            width: 100%;
            height: 200px;
            border-radius: 4px 4px 0 0;
            object-fit: cover;
        }
          &__text {
            padding: 16px;
            color: #3F3F3F;
        }
        &__title {
            font-weight: 600;
            font-size: 20px;
            line-height: 25px;
            margin-bottom: 16px;
        }
        &__description {
            font-size: 16px;
            line-height: 20px;
            margin-bottom: 32px;
        }
        &__price {
            font-weight: 600;
            font-size: 24px;
            line-height: 30px;
        }
    }
    .product:hover {
        transform: scale(0.9);
    }
</style>