<template>
  <ul id="showList">
    <li v-for="show in shows" :key="show.date">
      {{ show.date }}:
      <a :href="show.event">{{ show.title }}</a>
      , {{ show.venue }}, {{ show.location }}
    </li>
  </ul>
</template>


<script>
import Shows from '~/assets/json/shows.json'

export default {
  data: function() {
    return {
      shows: Shows
    }
  }
}
</script>
