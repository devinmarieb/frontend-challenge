<template>
  <button @click="$emit('uploadData')">
    <svg width="24px" height="24px" viewBox="0 0 24 24" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
      <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <polygon id="artboard" points="0 0 24 0 24 24 0 24"></polygon>
        <path d="M9,16 L15,16 L15,10 L19,10 L12,3 L5,10 L9,10 L9,16 Z M5,18 L19,18 L19,20 L5,20 L5,18 Z" id="arrow-upload" fill-rule="nonzero"></path>
      </g>
    </svg>
  </button>
</template>

<script>
  export default {
    name: 'UploadButton'
  }
</script>

<style scoped>
  button {
    padding-right: 20px;
    border: none;
    background: none;
  }
  button svg g path {
    fill: #8F97A8;
    transition: .3s ease;
  }
  button:hover svg g path {
    fill: #000;
  }
</style>