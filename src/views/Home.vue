<template>
  <div class="home">
    <Top :topT="wallet" :cardInfo="activecard" />
    <Card v-if="pickedCard" :card="pickedCard" />
    <CardStack @showCard="showCard" />
    <router-link id="addcard" to="/addcard">ADD NEW CARD</router-link>
  </div>
</template>
<script>
import Top from "@/components/Top.vue";
import Card from "@/components/Card.vue";
import CardStack from "@/components/CardStack.vue";

export default {
  data() {
    return {
      activecard: "ACTIVE CARD",
      wallet: "E - WALLET",
      pickedCard: null,
    };
  },
  components: { Top, Card, CardStack },
  methods: {
    showCard(newCard) {
      this.pickedCard = {
        validmonth: newCard.validmonth,
        validyear: newCard.validyear,
        holdername: newCard.holdername,
        cardnumber: newCard.cardnumber,
        vendor: newCard.vendor,
      };
    },
  },
};
</script>
<style scoped>
#addcard {
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
  height: 4rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  font-weight: 700;
  text-decoration: none;
  color: #000;
  border: 0.125rem solid #000;
  box-sizing: border-box;
  border-radius: 0.5rem;
  margin: 2rem 0;
}
#addcard:hover {
  background-color: #000;
  color: #d0d0d0;
}
</style>
