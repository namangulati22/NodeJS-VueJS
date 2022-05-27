<template>
  <div>
    <h1>NodeJS + VueJS</h1>
    <p class = "lead">{{fetch_status}}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data() {
    return{
      fetch_status: "fetching"
    }
  },
  created() {
    axios({
      method: 'get',
      url: 'http://localhost:9000/',
    })
      .then((response) => {
        this.fetch_status = "Hello World from backend"
        console.log("response.data")
      })
      .catch((error) => {
        this.fetch_status = "failed"
      })
  }
}
</script>

