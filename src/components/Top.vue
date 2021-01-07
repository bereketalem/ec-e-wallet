<template>
  <header class="top">
    <h1>{{ topT }}</h1>
    <p class="card-type">{{ cardInfo }}</p>
  </header>
</template>

<script>
export default {
  props: {
    topT: {
      type: String,
    },
    cardInfo: {
      type: String,
    },
  },
};
</script>

<style >
.card-type {
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  flex-direction: column;
  text-transform: uppercase;
}
.top p {
  -webkit-box-flex: 1;
  flex: 1;
  font-size: 0.8rem;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.4);
  padding: 0.25rem;
}
.top h1,
.top p {
  text-align: center;
  margin: 0;
}

h1 {
  display: block;
  margin-block-start: 0.67em;
  margin-block-end: 0.67em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  font-weight: bold;
  font-family: Source Sans Pro, sans-serif;
}
</style>
