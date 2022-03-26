<template>
  <ul>
    <li v-for="user in users" :key="user.id">{{user.name}}:{{user.id}}</li>
  </ul>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      users:[]
    }
  },
  mounted() {
    axios.get('http://120.55.55.33:3000/api/users').then(response=>{
      this.users = response.data
    })
  },
}
</script>

<style>
</style>
