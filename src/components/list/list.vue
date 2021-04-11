<template>
  <div class="list">
    <div class="list__title">
      <textarea class="title__textarea" placeholder="輸入標題" v-model="list.listName"></textarea>
      <a class="title__delete" @click="list.listStatus = !list.listStatus">
        <img src="../../assets/icon/cancel.svg">
      </a>
    </div>
    <div class="list__card">
      <div class="card" v-for="card in cards" :key="card.id" v-show="card.cardStatus">
        <a class="card__checkbox" @click="card.cardFinish = !card.cardFinish">
          <i>
            <img class="checkIcn" src="../../assets/icon/check.svg" v-show="card.cardFinish">
          </i>
        </a>
        <textarea class="card__textarea" v-bind:class="{card__textarea_finish: card.cardFinish}" rows="15" maxlength="512" placeholder="輸入內容" v-model="card.cardContent"></textarea>
        <a class="card__delete" @click="card.cardStatus = !card.cardStatus">
          <img src="../../assets/icon/cancel.svg">
        </a>
      </div>
    </div>
    <a class="plusBtn" @click="newCard">
      <img class="plusIcn" src="../../assets/icon/plus.svg">
      <p>新增卡片</p>
    </a>
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
        cardFinish:false,
        cardContent: "",
        cardStatus: true,
        cardColor: ""
      }

      this.cardId += 1
      cardData.id = this.cardId
      this.cards.push(cardData)
    }
  }
}

</script>
<style src='./list.css'>

</style>