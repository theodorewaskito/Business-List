<script>
  import Card from '../components/Card.vue'
  import Category from '../components/Category.vue'

  export default ({
    name: 'HomeView',
    props: ['dataBusiness', 'dataCategory', 'page', 'search'],
    components: {
      Card,
      Category
    },
    data() {
      return {
        inputSearch: this.search
      }
    },
    methods: {
      newPage(page) {
        let payload = {
          page: page
        }
        this.$emit("getBusinessDataByPage", payload)
      },
      formSearch() {
        this.$emit('getBusinessDataBySearch', {
          search: this.inputSearch
        })
      }
    }
  })
</script>

<template>
  <div >
    <div class="row">
      <div class="col-10">
        <form @submit.prevent="formSearch">
          <div class="input-group mb-3">
            <button class="btn btn-outline-secondary" type="submit" id="button-addon2">
              <i class="bi bi-search"></i>
            </button>
            <input 
              v-model="inputSearch"
              type="text" 
              class="form-control" 
              placeholder="Cari nama bisnis" 
              aria-label="Recipient's username" 
              aria-describedby="button-addon2" 
              style="background-color: #f1f5f9"
            >
          </div>
        </form>
      </div>
      <div class="col-2">
        <button 
          class="btn btn-outline-primary" 
          style="width: 100%"
          data-bs-toggle="modal"
          data-bs-target="#exampleModal"
        >
          <i class="bi bi-folder"></i>
          Kategori
        </button>

        <Category
          :dataCategory="dataCategory"
        />

      </div>
    </div>
    
    

    <Card
      :dataBusiness="dataBusiness"
    />  

    <div class="d-flex justify-content-between my-4">

      <div
        v-if="this.page === 1"
      >
        <p >Halaman 1 dari 3</p>      
      </div>
      <div
        v-if="this.page === 2"
      >
        <p >Halaman 2 dari 3</p>      
      </div>
      <div
        v-if="this.page === 3"
      >
        <p >Halaman 3 dari 3</p>      
      </div>

      <nav aria-label="Page navigation example">
        <ul class="pagination">
          <!-- <li class="page-item">
            <a class="page-link" href="#" aria-label="Previous">
              <span aria-hidden="true">&laquo;</span>
            </a>
          </li> -->
          <li 
            class="page-item"
            @click.prevent="newPage(1)"
          ><button class="page-link">1</button></li>
          <li 
            class="page-item"
            @click.prevent="newPage(2)"
          ><button class="page-link">2</button></li>
          <li 
            class="page-item"
            @click.prevent="newPage(3)"
          ><button class="page-link">3</button></li>
          <!-- <li class="page-item">
            <a class="page-link" href="#" aria-label="Next">
              <span aria-hidden="true">&raquo;</span>
            </a>
          </li> -->
        </ul>
      </nav>

    </div>

  </div>

</template>
