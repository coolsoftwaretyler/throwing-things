<template>
  <div>
    <h1>Upcoming shows</h1>
    <ul id="showList" v-if="upcomingShows.length > 0">
      <li v-for="show in upcomingShows" :key="show.date">
        <Show :show="show" />
      </li>
    </ul>
    <p>
      We don't have any shows coming up. Sorry about that!
      <nuxt-link to="/contact">Contact us</nuxt-link> to book or play a show with us.
    </p>
    <h1>Past shows</h1>
    <ul id="showList">
      <li v-for="show in pastShows" :key="show.date">
        <Show :show="show" />
      </li>
    </ul>
  </div>
</template>


<script>
import Show from "~/components/show.vue";
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

<style>
ul {
  list-style: none;
  padding-left: 0;
}
</style>
