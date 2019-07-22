<template>
  <div>
    <p>{{ show.title }}, {{ show.venue }}, {{ show.location }}</p>
    <time :datetime="show.date">{{ date }}</time><br />
    <a :href="show.event">Event</a>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      date: this.show.date
    };
  },
  props: ["show"]
};
</script>
