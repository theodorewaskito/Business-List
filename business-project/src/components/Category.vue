<script>

export default ({
  name: "Category",
  props: ['dataCategory'],

})

// console.log(data);
</script>

<template>
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog  modal-dialog-scrollable">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Filter</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <p style="color: #c3c8cf">Kategori Bisnis</p>
          <div 
            v-for="data in dataCategory"
            :key="data.paramCode" 
          >
            <div class="form-check mb-4">
              <input class="form-check-input" type="checkbox" :value=data.paramCode :id=data.paramCode>
              <label class="form-check-label" :for=data.paramCode>
                {{data.paramName}}
              </label>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-primary" style="width: 100%">Terapkan</button>
        </div>
      </div>
    </div>
  </div>
</template>