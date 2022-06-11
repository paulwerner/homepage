<template>
  <v-container class="content-container">
    <v-layout justify-center align-center column>
      <v-flex md12 md6>
        <v-avatar :size="avatarSize">
          <v-img src="../assets/avatar_small.png" alt="Paul Werner" />
        </v-avatar>
        <h1>{{ name }}</h1>
        <h2>{ {{ profession }} }</h2>
        <blockquote class="font" :cite="cite_src">
          <p>{{ cite }}</p>
          <small>{{ author }}</small>
        </blockquote>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Cite-Component",
  data() {
    return {
      avatarSize: "180px",
      name: "Paul Werner",
      profession: "SOFTWARE ENGINEER",
      cite:
        "Einstein's Three Rules of Work: " +
        "Out of clutter find simplicity. " +
        "From discord find harmony. " +
        "In the middle of difficulty lies opportunity.",
      author: "John Archibald Wheeler",
      cite_src:
        "[Interview in Cosmic Search, Vol. 1, No. 4 (Fall 1979). " +
        "Sometimes this quote is attributed to Albert Einstein himself. " +
        "Read more at http://izquotes.com/quote/327278]",
    };
  },
};
</script>

<style scoped></style>
