<template>
  <div v-for = '(aaa,index) in article'>
  <span>{{index + 1}}</span>
    <span>{{aaa.name}}</span>
    <span>{{aaa.email}}</span>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      article:'',
    }
  },
  created() {
    // Simple POST request with a JSON body using axios
    const article = { title: "Vue POST Request Example" };
    axios.post("http://backenddavid.codesk.am/api/articles", article)
      .then((response) => {
        console.log(response)
        this.article = response.data
        console.log(this.article)
      });
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
