<template>            
  <div class="content">
    <div class="header">
      <p>To Do List</p>
      <div class="header__newList">
        <input type="text" placeholder="新增清單" v-model="newListName" />
        <a class="plusBtn" @click="newList()">
          <img src="../assets/icon/plus.svg" />
        </a>
      </div>
    </div>
    <div class="allList">
      <list v-for="list in lists" :key="list.id" :list="list" v-show="list.listStatus"></list>
    </div>
  </div>
</template>

<script>
import List from "./list/list.vue";

export default {
  components: {
    List
  },

  data() {
    return {
      listId: 0,
      newListName: "",
      lists: []
    };
  },

  methods: {
    newList() {
      if(this.newListName.replace(/^\s*|\s*$/g,"") !== ""){
        let listData = {
          id: "",
          listStatus: true,
          listName: "",
          listColor: "background-color: rgb(182 215 249)",
          isSelectColor: false
        };
        listData.listName = this.newListName
        this.listId += 1
        listData.id = this.listId
        this.lists.push(listData);
        this.newListName = ""
      }
    },
  },
};
</script>

<style src='./to-do-list.css' scoped>
</style>
