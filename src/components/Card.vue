<template>
  <div class="card blank" @click="$emit('click')" :class="card.vendor">
    <header>
      <img alt="chip" src="../assets/chip-light.svg" />
      <img
        v-if="card.vendor"
        :src="require('../assets/vendor-' + card.vendor + '.svg')"
        alt=""
      />
    </header>
    <section class="number">
      {{ card.cardnumber }}
    </section>
    <section class="info">
      <aside class="holder">
        <span>Cardholder Name</span>
        <p>{{ card.holdername }}</p>
      </aside>
      <aside class="valid">
        <span>Valid until</span>
        <p>{{ card.validmonth }}/{{ card.validyear }}</p>
      </aside>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<style>
.blank {
  background: linear-gradient(
      237.75deg,
      hsla(0, 0%, 100%, 0.24),
      hsla(0, 0%, 100%, 0)
    ),
    #d0d0d0;
}
.card header img {
  opacity: 0.8;
}
.card {
  max-width: 24rem;
  height: 14rem;
  border-radius: 0.6rem;
  padding: 1rem;
  box-shadow: 0 0 0.5rem rgba(0, 0, 0, 0.4);
  display: grid;
  gap: 0.5rem 0;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 2.8rem;
  text-shadow: -1px -1px 2px hsla(0, 0%, 100%, 0.4);
}
.evil {
  background: linear-gradient(248.3deg, rgba(0, 0, 0, 0.16), transparent),
    #f33355;
  color: #fff;
}
.card header {
  display: flex;
  grid-column: auto/span 2;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: start;
  align-items: flex-start;
}
.card section.info aside.holder {
  text-align: left;
  flex: 1;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: PT Mono, monospace;
  padding: 1rem;
  height: 100vh;
  max-width: 24rem;
  margin: 0 auto;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
.card section.info,
.card section.number {
  grid-column: auto/span 2;
  grid-row: auto/span 1;
  display: flex;
}
.card section.number {
  font-size: 1.6rem;
  letter-spacing: 0.05rem;
  padding: 0.5rem 0 0;
  text-transform: uppercase;
}
body {
  background-color: peachpuff;
}
.evil {
  background-color: red;
}
.ninja {
  background-color: darkgrey;
}
.bitcoin {
  background-color: orange;
}
.blockchain {
  background-color: hotpink;
}
</style>


