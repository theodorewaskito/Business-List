<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <button type="button" class="btn btn-link" @click.prevent="home">
        <i class="bi bi-arrow-left" style="color: black"></i>
      </button>
      <button type="button" class="btn" @click.prevent="home">
        <h5>Daftar Bisnis</h5>
      </button>
      <button type="button" class="btn btn-link">
        <i class="bi bi-chat-left-dots" style="color: black"></i>
      </button>
    </div>
  </nav>
</template>

<script>
export default ({
  methods: {
    home() {
      this.$emit('getBusinessData')
    }
  }
})
</script>


