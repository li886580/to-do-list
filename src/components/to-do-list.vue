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
      <div class="list">
        <div class="list__title">
          <textarea class="title__textarea" rows="15" maxlength="512"  placeholder="輸入標題" v-model="listName"></textarea>
          <a class="title__delete">X</a>
        </div>
        <!-- <div class="list__item">
          <div class="item">
            <a class="item__checkbox"></a>
            <textarea class="item__textarea" rows="15" maxlength="512"  placeholder="輸入清單" v-model="itemContent"></textarea>
            <a class="item__delete">X</a>
          </div>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
let listJson = {
  "listName": "",
  "listColor": "",
  "item": [
    {
      "itemColor": "",
      "itemContent": "",
      "itemStatus": ""
    }
  ]
}


export default {
  data() {
    return {
      newListName: '',
      listName: '',
      itemContent: '',
      itemColor: ''
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
