<template>
    <v-layout-default>
        <v-container>
            

            <div class="categories">
                <img src="/public/organization.png" alt="org" width="220px">
                <img src="/public/lamp.png" alt="lamp" width="220px">
                <img src="/public/textil.png" alt="textil" width="220px">
                <img src="/public/kitchen.png" alt="kitchen" width="220px">
            </div>

            <h2>Трендовые товары</h2>

            <v-row>
                <v-col 
                    v-for="product in smartphones"
                    span="3"
                    md="6"
                    sm="12"
                >
                    <v-catalog-card 
                        :id="product.id"
                        :image="product.image"
                        :title="product.title"
                        :price="product.price"
                        :category="product.categoryId"
                    />
                </v-col>
            </v-row>
        </v-container>
    </v-layout-default>
</template>

<script setup>
    import { useCatalogCategory } from '@/composables';
    import VLayoutDefault from '@/components/Layouts/VLayoutDefault.vue';
    import VContainer from '@/components/VContainer.vue';
    import VRow from '@/components/UI/VRow.vue';
    import VCol from '@/components/UI/VCol.vue';
    import VCatalogCard from '@/components/VCatalogCard.vue';


    const { 
        products: smartphones, 
        getProductsCategory: getProductsCategorySmartphones
    } = useCatalogCategory();

    const { 
        products: laptops, 
        getProductsCategory: getProductsCategoryLaptops
    } = useCatalogCategory();

    getProductsCategorySmartphones(1);
    getProductsCategoryLaptops(2);
</script>

<style>
    .categories {
        display: flex;
        gap: 20px;
        justify-content: center;
        margin-top: 64px;
        margin-bottom: 64px;
    }
</style>