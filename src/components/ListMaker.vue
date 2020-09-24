<template>
  <div id="app-container">

    <div class="header">
      <p class="app-title">Transcriptions</p>
      <div>
        <UploadButton @uploadData="uploadData()"/>
        <DownloadButton @fetchData="fetchData()" @setHeight="setHeight()"/>
      </div>
    </div>

    <div class="text-items" v-for="(item, index) in info" :key="item.id">
      <div class="listitem-top">
        <div class="listitem-left">
          <Checkbox />
          <img class="person-icon" src="assets/person@2x.png" alt="person icon"/>
          <textarea class="item-voice" v-model="item.voice" style="font-size: 18px"></textarea>
        </div>
        <DeleteButton @deleteData="deleteData(index)"/>
      </div>
      <textarea class="item-text" v-model="item.text" style="font-size: 18px"></textarea>
    </div>

    <AddRowButton @addRow="addRow()"/>

  </div>
</template>

<script>
import DownloadButton from './DownloadButton';
import DeleteButton from './DeleteButton';
import AddRowButton from './AddRowButton';
import UploadButton from './UploadButton';
import Checkbox from './Checkbox';

export default {
  name: 'ListMaker',
  components: {
    DownloadButton,
    DeleteButton,
    AddRowButton,
    UploadButton,
    Checkbox   
  },
  mounted () {},
  methods: {
    fetchData() {
      fetch('http://www.mocky.io/v2/5ae1c5792d00004d009d7e5c')
      .then((res) => res.json())
      .then((data) => this.info = data)
    },
    setHeight() {
      setTimeout(()=> {
        let textArea = [].slice.call(document.querySelectorAll('.item-text'));
        textArea.map((el)=> {
          el.style.height = '1px';
          el.style.height = (25 + el.scrollHeight) + 'px';
        })
      }, 100)
    },
    addRow() { this.info.push({voice: 'Person', text: 'Message'}) },
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
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&family=Open+Sans&display=swap');
#app-container {
  position: relative;
  width: 100%;
  height: 100%;
}
.header {
  width: 100%;
  height: 80px;
  margin-bottom: 5vh;
  background: #fff;
  box-shadow: inset 0 -4px 4px -4px #000000;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.app-title {
  font-size: 20px;
}
.text-items {
  margin: 0 auto;
  padding: 2vh 2vh;
  width: 70%;
  background: #fff;
  border-bottom: 1px solid rgba(0,0,0,.2);
}
textarea {
  border: none;
  resize: none;
}
.item-voice {
  height: 20px;
  font-family: 'Montserrat', sans-serif;  
  color: #566074;
}
.item-text {
  width: 100%;
  /*height: 100px;*/
  box-sizing:border-box;
  text-align: left;
  padding: 0 50px 0 65px;
  font-family: 'Open Sans', sans-serif;
  color: #778195;
}
.listitem-top {
  width: 100%;
  padding-bottom: 2vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.listitem-left {
  display: flex;
  align-items: center;
}
.person-icon {
  width: 25px;
  margin: 0 7px 0 -5px;
  object-fit: contain;
}
</style>
