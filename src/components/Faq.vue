<template>
  <div class="faq">
    <div class="container">
      <section class="section">
        <h1 class="title">FAQ</h1>
        <h2 class="subtitle is-4">Lorum ipsum and all of that jazz.</h2>

        <div class="columns" v-if="faqs && faqs.length">
          <div class="column is-one-third" v-for="faq of faqs">
            <div class="card">
              <div class="card-content">
                <p class="title">{{ faq.title }}</p>
                <p class="answer">{{ faq.body }}</p>
              </div>
            </div>
          </div>
        </div>

      </section>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'faq',
  //arrow function we can use
  data: () => ({
    faqs: [],
    //if we have any errors
    errors: []
  }),

  //when this componet runs it going to call this method
  created() {
    //get request using axios
    axios.get("https://jsonplaceholder.typicode.com/posts")
      .then(response => {
        //slice to return only the top 10 
        this.faqs = response.data.slice(0,10);
      })
      //catch error that show up
      .catch(e => {
        this.error.push(e)
      })
  }
} 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
@import '../mq'

.pd 
  padding: 2.4em 0 1.5em 0

.answer
  margin-top: 10px !important
  color: gray

.columns
  flex-wrap: wrap

</style>
