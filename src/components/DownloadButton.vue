<template>
   <button @click="$emit('fetchData'); $emit('setHeight')">
    <svg width="24px" height="24px" viewBox="0 0 24 24" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
      <title>Download Content</title>
      <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <polygon id="artboard" points="0 0 24 0 24 24 0 24"></polygon>
        <path d="M4,6 L2,6 L2,20 C2,21.1 2.9,22 4,22 L18,22 L18,20 L4,20 L4,6 Z M20,2 L8,2 C6.9,2 6,2.9 6,4 L6,16 C6,17.1 6.9,18 8,18 L20,18 C21.1,18 22,17.1 22,16 L22,4 C22,2.9 21.1,2 20,2 Z M19,11 L15,11 L15,15 L13,15 L13,11 L9,11 L9,9 L13,9 L13,5 L15,5 L15,9 L19,9 L19,11 Z" id="button-plus" fill-rule="nonzero"></path>
      </g>
    </svg>
  </button>
</template>

<script>
  export default {
    name: 'DownloadButton'
  }
</script>

<style scoped>
  button {
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