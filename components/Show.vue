<template>
  <div>
    {{ show.date }}:
    <a :href="show.event">{{ show.title }}</a>
    , {{ show.venue }}, {{ show.location }}
  </div>
</template>

<script>
export default {
  props: ["show"]
}
</script>
