<template>
    <div class="prod-list">
        <transition-group name="fade">
            <VLouder
                v-if="isLoading"
            />
            <VProduct
                v-else v-for="product in products"      
                v-bind:key="product.id"
                :product="product"
                @remove="$emit('remove', product)"
            />
        </transition-group>
    </div>
</template>

<script>
import VProduct from "./v-product.vue";
import VLouder from "./v-louder.vue";
export default {
    name: "VproductList",
    components: { VProduct, VLouder },
    data() {
        return {
            isLoading: true
        }
    },
    props: {
        products: {
            type: Array,
            required: true,
        }
    },

    created() {
        setTimeout(() => {
            this.isLoading = false
        },1200)
    }
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
    .fade-enter-active,
    .fade-leave-active {
     transition: opacity 0.5s ease;
    }
    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }
     .fade-move {
        transition: transform 0.5s ease;
    }
</style>