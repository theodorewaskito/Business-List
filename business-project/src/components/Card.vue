<script>

export default ({
  name: "Card",
  props: ['dataBusiness',],

})

// console.log(data);
</script>


<template>
  <div class="row">
    <div 
      class="col-4"
      v-for="data in dataBusiness"
      :key="data.id" 
    >
      <div
        class="card m-3 p-3"  
        style="height: 300px"
      >
        <img :src=data.logoUrl class="card-img-top p-3 card" alt="logo">
        <div class="card-body d-flex flex-column bd-highlight mb-3">
          <p class="card-title bd-highlight"><b>{{data.businessName}}</b></p>
          <p class="card-text mt-auto bd-highlight" style="color: grey">{{data.businessCategoryName}}</p>
        </div>
      </div>
    </div>
  </div>

</template>
