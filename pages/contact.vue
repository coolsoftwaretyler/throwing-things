<template>
  <div>
    <p>Find us on:</p>
    <ul>
      <li v-for="item in social" :key="item.name">
        <a :href="item.link">{{ item.name }}</a>
      </li>
    </ul>
    <p>
      Or
      <a href="mailto:throwingthingsandstuff@gmail.com">email us</a>.
    </p>
  </div>
</template>

<script>
import social from "~/assets/json/social.json";
export default {
  data: function() {
    return {
      social: social
    };
  }
};
</script>
