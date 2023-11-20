<template>
    <router-view> </router-view>
    <Navbar></Navbar>
    <div class="container">
    <Beranda></Beranda>
    <Service></Service>
    <Portofolio></Portofolio>
    <Blog></Blog>
   </div>
   
   </template>
   
   <script>
   import Navbar from './components/layouts/Navbar.vue';
   import Beranda from './components/Beranda/Beranda.vue';
   import Service from './components/Beranda/Service.vue';
   import Portofolio from './components/Beranda/Portofolio.vue';
   import Blog from './components/Beranda/Blog.vue';

   import { Get } from '@/Api/index.js';
   export default{
     components: {
       Navbar,
       Beranda,
       Service,
       Portofolio,
       Blog,
     },data(){
    return{
        DataHome:[]
    }
  },
  async mounted(){
    const response = await Get('http://localhost;9000/api/home');
    console.log(response);
  },
   }
   </script>