<template>
  <div>
    <p>{{ quote }}</p>
    <button @click='newQuote'>Get New Quote</button>
  </div>
</template>

<script>
import request from 'request'
export default {
  name: 'Quote',
  data: function () {
    return {
      quote: ''
    }
  },
  methods: {
    newQuote: function () {
      try {
        request.get('http://ron-swanson-quotes.herokuapp.com/v2/quotes', (error, response, body) => {
          if (!error && response.statusCode === 200) {
             let result = JSON.parse(body)
             this.quote = result[0]
          }
        });
      } catch (err) {
        console.log(err)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
