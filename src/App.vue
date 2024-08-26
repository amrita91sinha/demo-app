<template>
  <div id="app">
    <MetaDataFormProcessor :components="formInputData.components" />
  </div>
</template>

<script>
import MetaDataFormProcessor from './components/MetaDataFormProcessor.vue';
import formData from './data/formMetaData.json';

export default {
  name: 'App',
  components: {
    MetaDataFormProcessor
  },
  data() {
    return {
      metadata: {},
      formInputData: null,
    };
  },
  created() {
    this.formInputData = formData;
  },
};
</script>
<style>
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f0f4f7;
  margin: 0;
  padding: 20px;
}

#app {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background: white;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}

h1 {
  font-size: 1.5em;
  color: #333;
  text-align: start;
  margin-bottom: 20px;
}

button {
  display: inline-block;
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  font-size: 1em;
  margin: 10px 0;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #45a049;
}

input[type="text"],
input[type="password"],
input[type="email"] {
  width: 100%;
  padding: 10px;
  margin: 5px 0 20px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  font-size: 1em;
}

input[type="submit"] {
  background-color: #007BFF;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1em;
}

input[type="submit"]:hover {
  background-color: #0056b3;
}

p {
  font-size: 1em;
  color: #333;
}
</style>
