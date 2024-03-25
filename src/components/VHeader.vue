<template>
    <div class="box">
      <header class="header">
        <div class="right-side">
          <img class="img" alt="Search" src="https://c.animaapp.com/MsujbGHX/img/search@4x.png" />
          <img class="img" alt="Person" src="https://c.animaapp.com/MsujbGHX/img/person@4x.png" />
          <img class="img" alt="Cart" src="https://c.animaapp.com/MsujbGHX/img/cart@4x.png" />
        </div>
        <div class="left-side">
          <img class="menu" alt="Menu" src="https://c.animaapp.com/MsujbGHX/img/menu@4x.png" />
          <div class="view">
            <img class="img" alt="Idea" src="https://c.animaapp.com/MsujbGHX/img/idea@4x.png" />
            <div class="text-wrapper">Идеи</div>
          </div>
        </div>
        <img class="rectangle" alt="Rectangle" src="https://c.animaapp.com/MsujbGHX/img/rectangle-9266@2x.png" />
      </header>
    </div>
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
  .box {
    height: 122px;
    position: relative;
    width: 1440px;
  }
  
  .box .header {
    background-color: #eff0f2;
    height: 122px;
    left: 0;
    position: fixed;
    top: 0;
    width: 1440px;
  }
  
  .box .right-side {
    align-items: center;
    display: inline-flex;
    gap: 32px;
    justify-content: center;
    left: 1160px;
    position: absolute;
    top: 45px;
  }
  
  .box .img {
    height: 30px;
    object-fit: cover;
    position: relative;
    width: 30px;
  }
  
  .box .left-side {
    align-items: center;
    display: inline-flex;
    gap: 46px;
    justify-content: center;
    left: 128px;
    position: absolute;
    top: 45px;
  }
  
  .box .menu {
    height: 28px;
    object-fit: cover;
    position: relative;
    width: 30px;
  }
  
  .box .view {
    align-items: center;
    display: inline-flex;
    flex: 0 0 auto;
    gap: 12px;
    justify-content: center;
    position: relative;
  }
  
  .box .text-wrapper {
    color: #000000;
    font-family: "Raleway", Helvetica;
    font-size: 24px;
    font-weight: 500;
    letter-spacing: -0.53px;
    line-height: 27.6px;
    position: relative;
    white-space: nowrap;
    width: fit-content;
  }
  
  .box .rectangle {
    height: 82px;
    left: 663px;
    object-fit: cover;
    position: absolute;
    top: 19px;
    width: 115px;
  }
  </style>
