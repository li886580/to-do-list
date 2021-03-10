<template>
  <div class="list">
    <div class="list__title">
      <textarea class="title__textarea" rows="15" maxlength="512"  placeholder="輸入標題" v-model="list.listName"></textarea>
      <a class="title__delete">X</a>
    </div>
    <div class="list__card">
      <div class="card" v-for="card in cards" :key="card.id" v-show="card.cardStatus">{{card}}
        <a class="card__checkbox"></a>
        <textarea class="card__textarea" rows="15" maxlength="512"  placeholder="輸入內容" v-model="card.cardContent"></textarea>
        <a class="card__delete" @click="card.cardStatus = !card.cardStatus">X</a>
      </div>
      <a class="plusBtn" @click="newCard">
        <img src="../../assets/icon/plus.svg" />
        <p>新增卡片</p>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      cardId: 0,
      cards: []
    }
  },
  
  props: {
    list: {
      type: Object,
      required: true
    }
  },
  
  methods: {
    newCard() {
      let cardData = {
        id: "",
        cardContent: "",
        cardStatus: true,
        cardColor: ""
      }

      this.cardId += 1
      cardData.id = this.cardId
      this.cards.push(cardData)
    },
  }
  // computed: {
  //   textareaText: {
  //     get(){
  //       // for (var i=0;i<this.id;i++){
  //           return this.list.listName
  //       //   }
  //     },
  //     set(val){
  //       this.$emit('update:lists',val)
  //     }
  //   }
  // }
}
</script>
<style src='./list.css'>

</style>