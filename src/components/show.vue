<template>
  <div>
    <div v-for="(d,index) in Info" :key="index">
      <center>
        <b-card class="container">
            <div v-if="d.gender==='Female'">
          <eva-icon name="heart" animation="pulse" fill="pink"></eva-icon>
          <p class="card-text">{{d.first_name}}</p>
          <p class="card-text">{{d.last_name}}</p>
          <p class="card-text">{{d.gender}}</p>
          <p class="card-text">{{d.email}}</p>
          <p class="card-text">{{d.ip_address}}</p>
          </div>
          <div v-if="d.gender==='Male'">
          <eva-icon name="shield" animation="pulse" fill="blue"></eva-icon>
          <p class="card-text">{{d.first_name}}</p>
          <p class="card-text">{{d.last_name}}</p>
          <p class="card-text">{{d.gender}}</p>
          <p class="card-text">{{d.email}}</p>
          <p class="card-text">{{d.ip_address}}</p>
          </div>
        </b-card>
      </center>
      <br>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { EvaIcon } from 'vue-eva-icons'
export default {
  data() {
    return {
      Info: []
    };
  },
  mounted() {
    axios.get("https://cs494-64e68.firebaseio.com/data.json")
    .then(response => {
      const data = response.data;
      for (let key in data) {
        const info = data[key];
        info.id = key;
        this.Info.push(info);
      }
    });
  }
};
</script>