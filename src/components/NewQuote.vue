<template>
  <div class="row margins">
    <form>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 margins"
      >
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote" />
      </div>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 margins"
      >
        <button @click.prevent="createNew" class="btn btn-primary mx-auto">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style>
.margins {
  margin-bottom: 10px;
}
</style>