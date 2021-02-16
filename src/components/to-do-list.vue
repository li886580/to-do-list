<template>
  <div class="content">
    <div class="header">
      <p>To Do List</p>
      <input type="text" placeholder="新增清單..">
    </div>
    <div class="allList">
      <div class="list">
        <div class="list__title">
          <textarea rows="15" maxlength="512"></textarea>
          <a>X</a>
        </div>
        <div class="list__item">
          <div class="item"></div>
          <div class="item"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src='./to-do-list.css'>
</style>
