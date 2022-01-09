<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: ''
    }
  },

  beforeMount() {
    this.$http.get('http://localhost:5000')
      .then((resp) => {
        this.msg = resp.data;
      })
      .catch(() => {
        this.msg = 'This is not supposed to be happened!'
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
