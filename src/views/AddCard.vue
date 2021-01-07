<template>
  <div class="AddCard">
    <Top :topT="addcard" :cardInfo="newcard" />
    <Card :card="cardsToSend" />

    <CardForm @newCardEx="addCards" />
    <a href="#" class="cta" @click="sendCard">Add Card</a>
  </div>
</template>

<script>
import CardForm from "@/components/CardForm.vue";
import Top from "@/components/Top.vue";
import Card from "@/components/Card.vue";
export default {
  name: "AddCard",
  components: { Card, CardForm, Top },

  data() {
    return {
      addcard: "ADD NEW CARD",
      newcard: "NEW CARD",
      cardsToSend: {},
    };
  },
  methods: {
    sendCard() {
      this.$root.allCards.push(this.cardsToSend);
      this.$router.push("/");
    },
    addCards(newCard) {
      this.cardsToSend = {
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
