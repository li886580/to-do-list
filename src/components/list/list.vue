<template>
  <div class="list">{{lists}}
    <div class="list__title">
      <textarea class="title__textarea" rows="15" maxlength="512"  placeholder="輸入標題" v-model="textareaText"></textarea>
      <a class="title__delete">X</a>
    </div>
    <div class="list__card">
      <div class="card">
        <a class="card__checkbox"></a>
        <textarea class="card__textarea" rows="15" maxlength="512"  placeholder="輸入清單" v-model="cardContent"></textarea>
        <a class="card__delete">X</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      // listName: '',
      // cardContent: '',
    }
  },
  props: {
    lists: {
      type: Array,
      required:true
    }
  },
  computed: {
    textareaText: {
      get(){
        // JSON.stringify(this.lists)
        return this.lists[0].listName
      },
      set(val){
        this.$emit('update:lists',val)
      }
    }
  }
}
</script>
<style src='./list.css'>

</style>