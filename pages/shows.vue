<template>
  <div>
    <ul id="showList">
      <li v-for="show in pastShows" :key="show.date">
        <Show :show="show" />
      </li>
    </ul>
  </div>
</template>


<script>
import Show from "~/components/Show.vue";
import shows from "~/assets/json/shows.json";

export default {
  components: {
    Show
  },
  computed: {
    sortedShows: function() {
      return shows.sort(function(a, b) {
        var x = a["date"];
        var y = b["date"];
        return x > y ? -1 : x < y ? 1 : 0;
      });
    },
    upcomingShows: function() {
      return this.sortedShows.filter(show => show.date > Date.now);
    },
    pastShows: function() {
      return this.sortedShows.filter(show => show.date < Date.now);
    }
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  padding-left: 0;
}
</style>
