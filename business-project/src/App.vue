<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import Navbar from './components/Navbar.vue'

  // export default defineComponent ({
  //   name: "App",
  //   data() {
  //     return {
  //       dataBusiness: [],
  //       dataCategory: [],
  //       dataBusinessbyCategory: []
  //     } 
  //   },

  //   methods: {
  //     getBusinessData() {
  //       fetch({
  //         method: "post",
  //         url: "http://sandbox.bizharedev.id:17001/business/parent/all",
  //         headers: {
  //           "Accept-Language" : "id"
  //         },
  //         data: {
  //           "businessName": "string",
  //           "size": 12,
  //           "page": 1,
  //           "listCategory": []
  //         }
  //       })
  //     }
  //   },

  //   components: {
  //     Navbar
  //   }
  // })
</script>

<template>

  <Navbar/>

  <div class="container my-3">
    <RouterView />
  </div>

</template>

<style>

</style>
