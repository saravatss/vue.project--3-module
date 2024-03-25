<template>
    <router-link 
        class="v-logo"
        to="/"
    />

    <div id="logo">
        <img :src="require('./assets//logo.png').default" alt="Logo">
    </div>
</template>

<style>
    .v-logo {
        width: 115px;
        height: 82px;
    }
</style>
    
<script>
    export default {
    }
</script>