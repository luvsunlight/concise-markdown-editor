<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Editor></Editor>
  </div>
</template>

<script>
import Editor from "./components/MarkdownEditor.vue";

export default {
    name: "app",
    components: {
        Editor
    }
};
</script>

<style>
#app {
    margin: 0 auto;
    padding: 40px;
    width: 60%;
    border-radius: 10px;
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    box-shadow: 1px 1px 1px #ddd;
}

img {
    width: 100px;
}

a {
    color: #42b983;
}
</style>
