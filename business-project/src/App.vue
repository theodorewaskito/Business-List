<script>

  import axios from './apis/server'
  import Navbar from './components/Navbar.vue'
  import HomeView from './views/HomeView.vue'

  export default ({
    name: "App",
    data() {
      return {
        dataBusiness: [],
        dataCategory: [],
        dataBusinessbyCategory: [],
        page: 0,
        name: ''
      } 
    },

    methods: {
      getBusinessData() {
        axios({
          method: "post",
          url: "/business/parent/all",
          headers: {
            "Accept-Language" : "id",
            "Content-Type": "application/json"
          },
          data: {
            "businessName": "string",
            "size": 12,
            "page": 1,
            "listCategory": []
          }
        })
          .then(({data}) => {
            this.dataBusiness = data.data.content
            console.log(this.dataBusiness);
          })
          .catch((err) => {
            console.log(err.response.data);
          })
      },

      getCategoryData() {
        axios({
          method: "get",
          url: "/media/param/business/category",
          headers: {
            "Accept-Language" : "id",
            "Content-Type": "application/json"
          }
        })
          .then(({data}) => {
            this.dataCategory = data.data
            console.log(this.dataCategory);
          })
          .catch((err) => {
            console.log(err.response.data);
          })
      },

      getBusinessDataByPage(payload) {
        const {page} = payload
        axios({
          method: "post",
          url: "/business/parent/all",
          headers: {
            "Accept-Language" : "id",
            "Content-Type": "application/json"
          },
          data: {
            "businessName": "string",
            "size": 12,
            "page": page,
            "listCategory": []
          }
        })
          .then(({data}) => {
            this.dataBusiness = data.data.content
            this.page = data.data.pageable.pageNumber + 1
          })
          .catch((err) => {
            console.log(err.response.data);
          })
      },

      getBusinessDataBySearch(payload) {
        const {search} = payload
        axios({
          method: "post",
          url: "/business/parent/all",
          headers: {
            "Accept-Language" : "id",
            "Content-Type": "application/json"
          },
          data: {
            "businessName": search,
            "size": 12,
            "page": 1,
            "listCategory": []
          }
        })
          .then(({data}) => {
            this.dataBusiness = data.data.content
            this.name = search
            this.page = 1
          })    
          .catch((err) => {
            console.log(err.response.data);
          })
      },
    },

    created() {
      if (this.page === 0 && this.businessName === "string") {
        this.getBusinessData()
      } else if (this.businessName !== "string") {
        this.getBusinessDataBySearch(this.name)
      } else {
        this.getBusinessDataByPage(this.page)
      }
      this.getCategoryData()
    },

    components: {
      Navbar,
      HomeView
    }
  })
</script>

<template>

  <Navbar
    @getBusinessData="getBusinessData"
  />

  <div class="container my-3">
    <HomeView 
      :dataBusiness="dataBusiness"
      :dataCategory="dataCategory"
      :page="page"
      @getBusinessDataByPage="getBusinessDataByPage"
      @getBusinessDataBySearch="getBusinessDataBySearch"
    />
  </div>

</template>

<style>

</style>
