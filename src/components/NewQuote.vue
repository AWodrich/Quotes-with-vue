<template>
  <div class="row">
      <form>
          <!--  v-model is a form attribute from vue js to bind data to the data object. so the data object gets updated everytime when data changes-->
          <!--  prevent is an event modifier to prevent that the event makes a request to the server and reloads the page.only execute the method -->
          <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
              <label>Quote</label>
              <textarea class="form-control" rows="3" v-model="quote" />
          </div>
          <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
              <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
          </div>
      </form>
  </div>
</template>

<script>
export default {
    data() {
        return {
            quote: ''
        };
    },
    methods: {
        createNew() {
            // send the new quote made here to the parent component using emit
            this.$emit('quoteAdded', this.quote)
            // reset quote
            this.quote = '';
        }
    }
}
</script>

<style>

</style>
