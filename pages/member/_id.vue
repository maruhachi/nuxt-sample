<template>
  <section class="container">
    <p>{{member[1].id}}</p>
    <p>{{member[1].name}}</p>
  </section>
</template>

<script>
  import axios from 'axios'

  export default {
    async asyncData({
      params
    }) {
      const {
        data: member
      } = await axios.get('http://localhost:8080/user', {
    //   } = await axios.get(`https://api.github.com/users/${params.id}`, {
          proxy: false
      })
      return {
        member
      }
    }
  }

</script>

<style scoped>
  .container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-direction: column;
  }

  .container img {
    margin-bottom: 20px;
    border-radius: 50%;
    overflow: hidden;
  }

</style>
