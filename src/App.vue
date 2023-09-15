<template>
  <header class="header">
    <page-header
      title="Our inspiring quotes"
      text="here you can find inspiring quotes"
    ></page-header>
  </header>
  <div class="quotes">
    <single-quote v-for="quote in quotes" :text="quote.quoteText" :key="quote.id">
    </single-quote>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";
import SingleQuote from "./components/SingleQuote.vue";
import quotes from "../quotes.json";
console.log(quotes);

export default {
  name: "App",
  components: {
    PageHeader: PageHeader,
    SingleQuote: SingleQuote,
  },
  data() {
    return {
      quotes,
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

h1,
h2,
h3,
h4,
h6,
h5 {
  margin-bottom: 1rem;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.quotes {
  max-width: 80%;
  margin: 1rem auto;
  display: grid;
  grid-template-columns: repeat(2,1fr);
}
</style>
