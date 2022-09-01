<template>
  <div id="app">
  
    {{ usersData }}
  </div>
</template>

<script>
import axios from 'axios'

const url = 'https://reqres.in/api/users?page=1'

export default {
  name: 'App',
  data() {
    return {
      alldata: null,
      usersData: null,
    }
  },
  components: {

  },
  methods: {
  
  },
  async created() {
    console.log("mounted");
    try {
      const res = await axios.get(url)
      this.alldata = res.data
      this.usersData = this.alldata.data
      console.log(res)
    } catch (error) {
      console.log(error);
    }
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
