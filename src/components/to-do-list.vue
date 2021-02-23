<template>
  <div class="content">
    <div class="header">
      <p>To Do List</p>
      <div class="header__newList">
        <input type="text" placeholder="新增清單.." v-model="newListName">
        <a class="plusBtn" @click="newList()">
          <img src="../assets/icon/plus.svg"/>
        </a>
      </div>
    </div>
    <div class="allList">
      <list></list>
    </div>
  </div>
</template>

<script>
import List from './list/list.vue'

let listJson = {
  "listName": "",
  "listColor": "",
  "card": [
    {
      "cardColor": "",
      "cardContent": "",
      "cardStatus": ""
    }
  ]
}

export default {
  components: {
    List
  },

  data() {
    return {
      newListName: '',
      listName: '',
      cardContent: '',
    }
  },
  
  methods: {
    newList() {
      listJson.listName = this.newListName
      localStorage.setItem('list1', JSON.stringify(listJson))
      this.newListName = ''
    }
  },
  // created() {
  //   this.listName = JSON.parse(localStorage.getItem('list1')).listName
  // }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src='./to-do-list.css'>
</style>
