<template>
  <div class="list" :style="list.listColor">
    <div class="list__title">
      <a class="more" v-on:click="list.isSelectColor = !list.isSelectColor">
        <div class="colorSelect" v-show="list.isSelectColor">
          <a class="color" v-for="color in colors" :key="color.item" v-on:click="list.listColor = color">
            <div class="color__style" v-bind:style="color"></div>
          </a>
        </div>
        <img src="../../assets/icon/more.svg">
      </a>
      <input class="title__textarea" placeholder="輸入標題" v-model="list.listName">
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
        <input class="card__textarea" v-bind:class="{card__textarea_finish: card.cardFinish}" placeholder="輸入內容" v-model="card.cardContent">
        <a class="card__delete" @click="card.cardStatus = !card.cardStatus">
          <img src="../../assets/icon/cancel.svg">
        </a>
      </div>
    </div>
    <a class="plusBtn" @click="newCard()">
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
      cards: [],
      colors: ["background-color: rgb(182 215 249)", "background-color: rgb(192 241 193)","background-color: rgb(255 184 133)","background-color: rgb(224 182 255)","background-color: rgb(255 233 74)","background-color: rgb(255 190 223)",]
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
        cardColor: "",
      }

      this.cardId += 1
      cardData.id = this.cardId
      this.cards.push(cardData)
    },
  }
}

</script>
<style src='./list.css'>

</style>