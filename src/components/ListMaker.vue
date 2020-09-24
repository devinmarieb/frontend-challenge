<template>
  <div>
    <button v-on:click="fetchData()">download</button>

    <div class="text-items" v-for="(item, index) in info" :key="item.id">
      <input type="checkbox" id="test" name="test" value="Test"/>
      <textarea v-model="item.voice" :placeholder="item.voice"></textarea>
      <textarea v-model="item.text" :placeholder="item.text"></textarea>
      <button v-on:click="deleteData(index)">delete</button>
    </div>

    <button v-on:click="addRow()">+</button>
    <button v-on:click="uploadData()">upload</button>
  </div>
</template>

<script>
export default {
  name: 'Info',
  mounted () {},
  methods: {
    fetchData() {
      fetch('http://www.mocky.io/v2/5ae1c5792d00004d009d7e5c')
      .then((res) => res.json())
      .then((data) => this.info = data)
    },
    addRow() { this.info.push({voice: '', text: ''}) },
    deleteData(index) { this.info.splice(index, 1) },
    uploadData() {
      fetch('http://www.mocky.io/v2/5ae1c5792d00004d009d7e5c', {
        method: 'POST',
        headers: { 
          'Accept': 'application/json',
          'Content-Type': 'application/json' 
        },
        body: JSON.stringify(this.info)
      }).then((res)=> {
        return res;
      })
    }
  },
  data() {
    return {
      info: null,
      range: 0
    }
  }
}
</script>

<style scoped>
</style>
