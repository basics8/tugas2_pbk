<template>
  <div id="app">
    <h1>{{ pageTitle }}</h1>
    <input type="text" v-model="inputText" :class="{ 'red-border': isRed }" @input="handleChange" placeholder="Type something...">
    <p :style="{ color: textColor }">You typed: {{ inputText }}</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      pageTitle: 'Interactive Web',
      inputText: '',
      isRed: false,
      textColor: 'white'
    };
  },
  methods: {
    handleChange() {
      // Toggle red border class based on input text length
      this.isRed = this.inputText.length > 10;

      // Change text color based on input text length
      this.textColor = this.inputText.length > 5 ? 'green' : 'black';
    }
  }
}
</script>

<style>
#app {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif, sans-serif;
  text-align: center;
  margin-top: 20px;
}

.red-border {
  border: 2px solid red;
}
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #ee9922;
  color: #ffffff;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  font-size: 36px;
  color: #f3ddb9;
  text-align: center;
  margin-bottom: 20px;
}

input[type="text"] {
  padding: 10px;
  width: calc(100% - 20px);
  max-width: 400px;
  margin: 0 auto;
  display: block;
  border: 1px solid #000000;
  border-radius: 5px;
  font-size: 16px;
}

p {
  font-size: 18px;
  text-align: center;
  margin-top: 20px;
}

.red-border {
  border-color: red;
}

.green-text {
  color: green;
}

</style>

