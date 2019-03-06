<template>
  <div class="about">
    <ul class="list-group">
      <li
        class="list-group-item"
        v-for="(u,index) in users"
        :key="index"
      >{{u.username}} - {{u.mail}}</li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      users: []
    };
  },
  mounted() {
    axios
      .get("https://cs494-64e68.firebaseio.com/data.json")
      .then(response => {
        console.log(response);
        const data = response.data;
        for (let key in data) {
          const user = data[key];
          user.id = key;
          this.users.push(user);
        }
      })
      .catch(error => {
        console.log(error);
      });
  },
};
</script>