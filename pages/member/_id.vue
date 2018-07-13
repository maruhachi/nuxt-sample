<template>
  <div class="container is-widescreen">
    <h2 class="title">{{ datas.group }}</h2>
    <table class="table is-striped">
      <tr>
        <th>id</th>
        <th>name</th>
      </tr>
      <tr v-for="mem in datas.members" :key="mem.id">
        <td>{{ mem.id }}</td>
        <td>{{ mem.name }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  async asyncData({ params }) {
    const { data: datas } = await axios.get("http://localhost:8080/member", {
      proxy: false
    });
    // const { data: one } = await axios.get("http://localhost:8080/member/4", {
    //   proxy: false
    // });
    return {
      datas
      // , one
    };
  }
};
</script>

<style scoped>
</style>
