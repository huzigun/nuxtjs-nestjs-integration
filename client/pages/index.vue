<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      {{ hello }}
    </v-col>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  name: 'Index',
  async asyncData({ $axios }) {
    try {
      const { data: hello } = await $axios.get('/');
      return { hello };
    } catch (error) {
      console.dir(error);
    }
  },
});
</script>
