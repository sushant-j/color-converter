<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Pick a color to begin
    </p>
  </div>
</template>

<script>
export default {
  name: 'HomeComponent',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
</style>
