<style>
*{
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  display: flex;
  justify-content: center;
}

#app * {

  width: 60%;
}

</style>

<template>
  <div id="app">
    <Form/>
  </div>
</template>

<script>
import Form from './components/Form/Form'
export default {
  name: 'App',
  components: {
    Form
  }
}
</script>