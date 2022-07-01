<script setup>
  import Card from '../components/Card.vue'
</script>

<template>
  <div >
    <div class="row">
      <div class="col-10">
        <div class="input-group mb-3">
          <button class="btn btn-outline-secondary" type="button" id="button-addon2">
            <i class="bi bi-search"></i>
          </button>
          <input type="text" class="form-control" placeholder="Cari nama bisnis" aria-label="Recipient's username" aria-describedby="button-addon2" style="background-color: #f1f5f9">

        </div>
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

        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog  modal-dialog-scrollable">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">Filter</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
              </div>
              <div class="modal-body">
                <p style="color: #c3c8cf">Kategori Bisnis</p>
                <div class="form-check">
                  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
                  <label class="form-check-label" for="flexRadioDefault1">
                    Default radio
                  </label>
                </div>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-primary" style="width: 100%">Terapkan</button>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
    
    

    <Card/>  

    <!-- <p>Test</p> -->

  </div>

</template>
