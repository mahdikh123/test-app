<template>
  <div>
    <button @click="fetchData">Fetch Data Click</button>
    <div v-if="data">{{ data }}</div>
  </div>
</template>
 
<script>
import axios from 'axios';

export default {
  data() {
    return {
      data: null,
    };
  },
  methods: {
    fetchData() {
      axios.get('https://sat7.faulio.com/api/v1/home')
        .then(response => {
          this.data = response.data;
        })
        .catch(error => {
          console.error('Error:', error);
        });
    },
  },
};
</script>
