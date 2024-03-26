<template>
    <div class="v-full-menu">
        <nav class="v-menu">

            <div class="v-menu__item">Организация и хранение</div>
            <div class="v-menu__item">Освещение и аудио</div>
            <div class="v-menu__item">Текстиль</div>

            <router-link to="/catalog/1" class="v-menu__item">
                Кухонные мелочи
            </router-link>

            <div class="v-menu__item">Для ванной</div>
            <div class="v-menu__item">Атмосфера и релаксация</div>
            <div class="v-menu__item">Растения и цветы</div>
            <div class="v-menu__item">На стену</div>
        </nav>

        <nav class="v-menu v-menu-2">
            <div class="v-menu__item">Скидки</div>
            <div class="v-menu__item">Идеи для вдохновения</div>
            <div class="v-menu__item">Статьи</div>

            <nav class="v-menu v-menu-3">
                <div class="v-menu__item">О нас</div>
                <div class="v-menu__item">Оплата и доставка</div>
                <div class="v-menu__item">Возврат и обмен</div>
            </nav>
        </nav>
    </div>
</template>

<script setup>
    import { useAuth } from '@/composables';

    const { isAuth } = useAuth();
</script>

<style>
    .v-menu {
        display: flex;
        flex-flow: row wrap;
        gap: 20px 20px;
        margin-left: 90px;
        margin-top: 128px;
        flex-direction: column;
        font-size: 20px;
    }

    .v-menu-2 {
        margin-left: 128px;
    }

    .v-menu__item {
        color: var(--color-black);
        text-decoration: none;
    }

    .v-menu__item.router-link-active {
        color: var(--color-blue);
    }

    .v-full-menu {
        display: flex;
        flex-flow: row wrap;
    }

    .v-menu-3 {
        margin-top: 88px;
        margin-left: 0px;
    }
</style>