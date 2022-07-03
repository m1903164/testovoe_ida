<template>
    <div class="prod-list">
        <VProduct
            v-for="product in products"      
            v-bind:key="product.id"
            :product="product"
            @remove="$emit('remove', product)"
        />
    </div>
</template>

<script>
import VProduct from "./v-product.vue";
export default {
    name: "VproductList",
    props: {
        products: {
            type: Array,
            required: true,
        }
    },
    components: { VProduct }
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
</style>