<template>
    <header class="v-header">
        <v-container>
            <v-row align="center" justify="beetwen" no-gutters>
                    <v-sidebar-menu/>

                    <v-logo/>

                    <router-link 
                        v-if="isAuth"
                        to="/profile" 
                        class="v-menu__item"
                    >
                        <template v-if="user">
                            {{ user.firstname }}
                        </template>
                    </router-link>

                    <router-link 
                        v-else
                        to="/auth/sign-in" 
                        class="v-menu__item"
                    >
                        Вход
                    </router-link>
            </v-row>
        </v-container>
    </header>
</template>

<script setup>
    import { ref } from 'vue';
    import { useRouter } from 'vue-router';
    import { useAuth } from '@/composables';
    import VRow from '@/components/UI/VRow.vue';
    import VLogo from '@/components/VLogo.vue';
    import VSidebarMenu from '@/components/VSidebarMenu.vue';
    import VContainer from '@/components/VContainer.vue';

    const search = ref();

    const router = useRouter();
    const { isAuth, user } = useAuth();

    function onSearch () {
        router.push({
            path: '/search',
            query: {
                q: search.value
            }
        });
    }
</script>

<style>
    .v-header {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 100;

        background-color: #F0F0F2;

        padding: 10px 0;
        border-bottom: 1px solid;
    }
</style>