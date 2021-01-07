<template id="app">
 
    <main id="add-card" autocomplete="off">
      
      <section class="card-form">
        <label for="number" class="col-2">Card Number</label>
        <input
          type="text"
          name="number"
          maxlength="16"
          placeholder="XXXX XXXX XXXX XXXX"
          class="col-2"
          v-model="myCard.cardnumber"
          @input="$emit('newCardEx', myCard)" 
        />
        <label for="cardholder" class="col-2">Cardholder Name</label>
        <input
          type="text"
          name="cardholder"
          placeholder="Firstname Lastname"
          class="col-2"
          v-model="myCard.holdername"
          @input="$emit('newCardEx', myCard)"   
        />
        <label for="month" class="col-1" >Month</label>
        <label for="year" class="col-1" >Year</label>
        <select name="month" class="col-1" v-model="myCard.validmonth" @change="$emit('newCardEx',  myCard)">
          <option value="01">01</option>
          <option value="02">02</option>
          <option value="04">04</option>
          <option value="06">06</option>
          <option value="08">08</option>
          <option value="10">10</option>
          <option value="12">12</option>
        </select>
        <select name="year" class="col-1" v-model="myCard.validyear" @change="$emit('newCardEx',  myCard)">
          <option value="21">21</option>
          <option value="22">22</option>
          <option value="23">23</option>
          <option value="24">24</option>
          <option value="25">25</option>
        </select>
        <label for="vendor" class="col-2">Vendor</label>
         <select name="vendor" class="col-2" v-model="myCard.vendor" @change="$emit('newCardEx',  myCard)"> 
          <option value="bitcoin">Bitcoin</option>
          <option value="evil">Evil</option>
          <option value="ninja">Ninja</option>
          <option value="blockchain">Blockchain</option>
       </select>
        
      </section>
     
    </main>
</template>

<script>


export default {
  data() {
    return {
      myCard: {
        validmonth: "",
        validyear: "",
        holdername: "",
        cardnumber: "",
        vendor: "",
      },
     
    };
  },
  
};
</script>

<style >
.card {
  max-width: 24rem;
  height: 14rem;
  border-radius: 0.6rem;
  padding: 1rem;
  box-sizing: border-box;
  display: grid;
  gap: 0.5rem 0;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 2.8rem;
  text-shadow: -1px -1px 2px hsla(0, 0%, 100%, 0.4);
}
.card header [alt="chip"] {
  align-self: flex-end;
  opacity: 1;
}
.card section.info,
.card section.number {
  grid-column: auto/span 2;
  grid-row: auto/span 1;
  display: flex;
}

p {
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
#app {
  -webkit-font-smoothing: antialiased;
  font-family: PT Mono, monospace;
  padding: 1rem;
  height: 100vh;
  max-width: 24rem;
  margin: 0 auto;
  box-sizing: border-box;
}
.top h1 {
  -webkit-box-flex: 2;
  flex: 2;
  line-height: 2rem;
  font-size: 2rem;
  padding: 1.5rem 0;
}
.top {
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  flex-direction: column;
  text-transform: uppercase;
}
.top h1,
.top p {
  text-align: center;
  margin: 0;
}
h1,
h2,
h3 {
  font-family: Source Sans Pro, sans-serif;
}
h1 {
  display: block;
  margin-block-start: 0.67em;
  margin-block-end: 0.67em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  font-weight: bold;
}
.card-form {
  margin: 2rem 0 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0 1rem;
}
.card-form label {
  padding: 0.25rem 0;
  font-size: 0.7rem;
  text-transform: uppercase;
}
.col-2 {
  grid-column: auto/span 2;
}
.col-1 {
  grid-column: auto/span 1;
}
label {
  cursor: default;
}
.card-form input,
select {
  border: 1px solid #000;
  border-radius: 0.25rem;
  padding: 0.5rem;
  height: 2.6rem;
  margin: 0 0 0.8rem;
  box-sizing: border-box;
  font-size: 1rem;
  width: 100%;
}
input {
  -webkit-writing-mode: horizontal-tb !important;
  text-rendering: auto;
  color: -internal-light-dark(black, white);
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: start;
  appearance: textfield;
  background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
  -webkit-rtl-ordering: logical;
  cursor: text;
  font: 400 13.3333px Arial;
}
select {
  -webkit-writing-mode: horizontal-tb !important;
  text-rendering: auto;
  color: -internal-light-dark(black, white);
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: start;
  appearance: menulist;
  align-items: center;
  white-space: pre;
  -webkit-rtl-ordering: logical;
  background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
  cursor: default;
  font: 400 13.3333px Arial;
}
a.cta {
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
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
a.cta:hover {
  background-color: #000;
  color: #d0d0d0;
}
a:-webkit-any-link {
  cursor: pointer;
}
main {
  display: block;
}
</style>
