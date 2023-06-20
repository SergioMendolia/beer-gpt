<template>

    <dl>
      <dt>You asked:</dt>
      <dd>{{asked}}</dd>
      <dt>BeerGPT says:</dt>
      <dd v-html="response" />
    </dl>

</template>

<script>
export default {
  name: 'DisplayResponse',
  props: {
    asked: String,
    response: String,
  },
}
</script>

<style :scoped>
  dl{
    text-align: left;
    width:80%;
    margin:40px auto;
  }
  dt{
    font-weight: bold;
    margin-top: 5px;
    font-weight: 0.5rem;
  }
  dd{
    margin: 10px 30px;
    font-size: 1.2rem;
  }
</style>
