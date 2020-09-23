<template>
  <div>
    <p v-for="item in info" :key="item.id">
      {{ item.id }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Info',
  mounted () {
    fetch(`http://www.mocky.io/v2/5ae1c5792d00004d009d7e5c`)
      .then((res) => res.json())
      .then((data) => {
        this.info = data;
      })
  },
  data() {
    return {
      info: []
    }
  }
}
</script>

<style scoped>
</style>
