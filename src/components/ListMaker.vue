<template>
  <div>
    <div v-for="item in info" :key="item.id">
      <input type="checkbox" id="test" name="test" value="Test">
      <p>{{ item.voice }}</p>
      <p>{{ item.text }}</p>
    </div>
    <button v-on:click="fetchData()">+</button>
  </div>
</template>

<script>
export default {
  name: 'Info',
  mounted () {},
  methods: {
    fetchData() {
      fetch(`http://www.mocky.io/v2/5ae1c5792d00004d009d7e5c`)
      .then((res) => res.json())
      .then((data) => {
        this.info = data;
        console.log(data)
      })
    }
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
