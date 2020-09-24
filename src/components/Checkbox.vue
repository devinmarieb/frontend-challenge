<template>
  <label class="container">
    <input type="checkbox">
    <span class="checkmark"></span>
  </label>
</template>

<script>
  export default {
    name: 'Checkbox'
  }
</script>

<style scoped>
.container {
  position: relative;
  padding-left: 35px;
  user-select: none;
}
/* Hide the browser's default checkbox */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}
/* Create a custom checkbox */
.checkmark {
  position: absolute;
  top: 50%;
  left: 0;
  height: 16px;
  width: 16px;
  border: 2px solid #859EFF;
  border-radius: 4px;
  transform: translate(0, -50%);
}
/* On mouse-over, add a grey background color */
.container:hover input ~ .checkmark {
  background-color: rgba(133,158,255,.5);
}
/* When the checkbox is checked, add a blue background */
.container input:checked ~ .checkmark {
  background-color: #859EFF;
}
/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}
/* Show the checkmark when checked */
.container input:checked ~ .checkmark:after {
  display: block;
}
/* Style the checkmark/indicator */
.container .checkmark:after {
  left: 6px;
  top: 2px;
  width: 2px;
  height: 8px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}
</style>