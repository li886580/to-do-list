<template>
  <div class="content">
    <div class="header">
      <p>To Do List</p>
      <div class="header__newList">
        <input type="text" placeholder="新增清單.." v-model="newListName" />
        <a class="plusBtn" @click="newList()">
          <img src="../assets/icon/plus.svg" />
        </a>
      </div>
    </div>
    <div class="allList">{{lists}}
      <list v-for="list in lists" :key="list.id" :lists.sync="lists"></list>
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
      id: 0,
      newListName: "",
      lists: []
    };
  },

  methods: {
    newList() {
      let listData = {
        id: "",
        listName: "",
        listColor: "",
        card: [
          {
            cardColor: "",
            cardContent: "",
            cardStatus: ""
          },
        ],
      };
      listData.listName = this.newListName
      this.id += 1
      listData.id = this.id
      this.lists.push(listData);
      // console.log(this.lists)
      // localStorage.setItem('list1', JSON.stringify(listData))
      // this.newListName = ''
    },
  },
  // created() {
  //   this.listName = JSON.parse(localStorage.getItem('list1')).listName
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src='./to-do-list.css'>
</style>
