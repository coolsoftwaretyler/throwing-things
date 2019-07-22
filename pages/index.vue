<template>
  <div class="container">
    <div class="intro" v-html="copy"></div>
    <iframe
      style="border: 0; width: 350px; height: 786px; margin: 2em auto; max-width: 100%;"
      src="https://bandcamp.com/EmbeddedPlayer/album=3807523161/size=large/bgcol=ffffff/linkcol=0687f5/transparent=true/"
      seamless
    >
      <a
        href="http://throwingthings.bandcamp.com/album/the-bruno-demos"
      >The Bruno Demos by Throwing Things</a>
    </iframe>
  </div>
</template>

<script>
import copy from "~/assets/markdown/index.md";

export default {
  data: function() {
    return {
      copy: copy
    };
  }
};
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  max-width: 650px;
}
.intro {
  ul {
    list-style: none;
    margin-left: 0;
    margin-top: 2em;
    padding-left: 0;
    li {
      margin-left: 0;
    }
  }
}
</style>
