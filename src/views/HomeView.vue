<template>
  <div class="home">
  {{ usersData}}
  <Footer></Footer>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import Footer from '@/components/Footer.vue';

const url = 'https://reqres.in/api/users?page=1'

export default {
  name: 'HomeView',
  data() {
    return {
      alldata: null,
      usersData: null,
    }
  },
  components: {
    Footer
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
