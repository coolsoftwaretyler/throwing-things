<template>
  <ul id="showList">
    <li v-for="show in shows" :key="show.date">
      <Show :show="show" />
    </li>
  </ul>
</template>


<script>
import Show from "~/components/show.vue";
import shows from "~/assets/json/shows.json";

export default {
  components: {
    Show
  },
  data: function() {
    return {
      shows: shows
    };
  }
};
</script>
