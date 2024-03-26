<template>
    <article class="v-catalog-card">
        <br>
        <router-link :to="`/catalog/${category}/${id}`">
            <img class="v-catalog-card__image" :src="image" >
        </router-link>
        <br>
        <router-link :to="`/catalog/${category}/${id}`">
            {{ title }}
        </router-link>

        <br>

        <div>
            {{ price }} ₽
        </div>

        <v-button
            theme="primary"
            size="large"
            wide
            @click="onAddToCart"
        >
            <img src="/public/icons/add to cart.png" alt="add-to-cart" class="catalog-img">
        </v-button>
        <br>
    </article>
</template>

<script setup>
    import VButton from '@/components/UI/VButton.vue';

    const props = defineProps({
        category: {
            type: [String, Number]
        },
        id: {
            type: Number
        },
        price: {
            type: Number
        },
        title: {
            type: String
        },
        image: {
            type: String
        }
    });

    const emit = defineEmits([
        'addToCart'
    ]);


    function onAddToCart () {
        emit('addToCart', {
            title: props.title,
            image: props.image,
            price: props.price,
            id: props.id,
            quantity: 1
        });
    }

</script>

<style>
.v-catalog-card {
    border: 0px solid;
}

    .v-catalog-card__image {
    display: block;
    width: 281px;
    height: 204px;
    object-fit: cover;
    border-radius: 8px;
}

.v-button {
    display: block;
    width: 28px;
    height: 28px;
    background-color: transparent;
    border: 0px;
    float: right
}

.v-button:hover {
    background-color: transparent;
}

.catalog-img {
    width: 28px;
    padding: 0px;
}

</style>