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
  computed: {
    shows: function() {
      return shows.sort(function(a, b) {
        var x = a["date"];
        var y = b["date"];
        return x > y ? -1 : x < y ? 1 : 0;
      });
    }
  }
};
</script>

<style>
ul {
  list-style: none;
  padding-left: 0;
}
</style>
