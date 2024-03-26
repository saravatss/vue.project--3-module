<template>
    <nav class="v-menu">

        <div class="v-menu__item">Организация и хранение</div>
        <div class="v-menu__item">Освещение и аудио</div>
        <div class="v-menu__item">Текстиль</div>

        <router-link to="/catalog" class="v-menu__item">
            Кухонные мелочи
        </router-link>

        <div class="v-menu__item">Для ванной</div>
        <div class="v-menu__item">Атмосфера и релаксация</div>
        <div class="v-menu__item">Растения и цветы</div>
        <div class="v-menu__item">На стену</div>
    </nav>
</template>

<script setup>
    import { useAuth } from '@/composables';

    const { isAuth } = useAuth();
</script>

<style>
    .v-menu {
        display: flex;
        flex-flow: row wrap;
        gap: 0 10px;
    }

    .v-menu__item {
        color: var(--color-black);
        border: 0px;
    }

    .v-menu__item.router-link-active {
        color: var(--color-blue);
    }
</style>