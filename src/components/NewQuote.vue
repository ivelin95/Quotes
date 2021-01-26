<template>
  <div class="row">
    <form>
      <div
        class="col-sm-8 com-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
      >
        <label>Quote</label>
        <textarea class="form-control" rows="4" v-model="quote"></textarea>
        
          <button class="btn button-primary btn_pos" @click.prevent="createNew">
            Add Quote
          </button>
        
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      quote: "",
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdd", this.quote);
      this.quote = "";
    },
  },
};
</script>

<style scoped>
      .btn_pos{
            position: relative;
            left: 40%;
      }
</style>

