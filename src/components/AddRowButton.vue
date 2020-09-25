<template>
  <button @click="$emit('addRow')">
    <svg width="32px" height="32px" viewBox="0 0 32 32" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
      <title>Add Row</title>
      <circle id="button-background" cx="16" cy="16" r="16"></circle>
      <polygon id="plus" fill="#FFFFFF" points="20.52 16.84 17.04 16.84 17.04 20.24 14.46 20.24 14.46 16.84 11 16.84 11 14.4 14.46 14.4 14.46 11 17.04 11 17.04 14.4 20.52 14.4"></polygon>
    </svg>
  </button>
</template>

<script>
  export default {
    name: 'AddRowButton'
  }
</script>

<style scoped>
  button {
    margin-top: 5vh;
    border: none;
    background: none;
  }
  button svg circle {
    fill: #D0D4DA;
    transition: .3s ease;
  }
  button:hover svg circle {
    fill: #000;
  }
</style>