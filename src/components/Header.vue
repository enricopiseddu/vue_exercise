<template>
  <header>
      <h1>
          {{ msg }}
      </h1>
  </header>

</template>


<script>

export default {
  name: 'AppHeader', //il componente deve essere multi-word
  props: {
      msg: String,
  },
}
</script>

<style scoped>
  header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
  }
</style>
