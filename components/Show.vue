<template>
  <div>
    <p>{{ show.title }}, {{ show.venue }}, {{ show.location }}</p>
    <time :datetime="show.date">{{ date }}</time>
    <br />
    <a :href="show.event">Event</a>
  </div>
</template>

<script>
export default {
  computed: {
    date: function() {
      return new Date(this.show.date).toDateString();
    }
  },
  props: ["show"]
};
</script>

<style lang="scss" scoped>
div {
  border-bottom: 2px black solid;
  margin-bottom: 2em;
  padding: 0 0 1em 0;
}
</style>
