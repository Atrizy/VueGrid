<template>
  <div id="app">
    <div class="tweet" v-if="clicked === true">
      <user-tweets
        v-for="tweet in tweets"
        :key="tweet['author']"
        :author="tweet['author']"
        :content="tweet['content']"
        :timestamp="tweet['timestamp']"
      >
      </user-tweets>
    </div>
    <div class="tweets" v-else>
      <user-tweets
        v-for="tweet in tweets"
        :key="tweet['author']"
        :author="tweet['author']"
        :content="tweet['content']"
        :timestamp="tweet['timestamp']"
      >
      </user-tweets>
    </div>
    <button @click="tweet_switch">Change layout</button>
  </div>
</template>

<script>
import UserTweets from "./components/UserTweets.vue";

export default {
  name: "App",
  methods: {
    //This bit right here is what makes the tweet switches toggle
    tweet_switch() {
      if (this.clicked === false) {
        this.clicked = true;
      } else {
        this.clicked = false;
      }
    },
  },
  data() {
    return {
      clicked: false,
      tweets: [
        {
          author: "@OliviaWidle",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2021",
        },
        {
          author: "@Memer",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2020",
        },
        {
          author: "@Memer",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2020",
        },
        {
          author: "@Memer",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2020",
        },
        {
          author: "@Memer",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2020",
        },
        {
          author: "@Memer",
          content:
            "In a thousand years archeologists will dig up tanning beds and think we used them to fry people as punishment.",
          timestamp: "5/14/2020",
        },
      ],
    };
  },
  components: {
    UserTweets,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  margin-top: 15px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: black;
}

.tweets {
  display: grid;
  grid-auto-rows: auto;
}

.tweet {
  display: grid;
  grid-template-columns: 200px 200px;
  gap: 30px;
  justify-self: center;
  align-self: center;
  text-align: center;
  padding-top: 10px;
  margin-left: 10px;
}

.tweet h6 {
  padding-bottom: 8px;
}

.tweet p {
  width: 200px;
}

.tweet h5 {
  padding-top: 10px;
  padding-bottom: 0px;
}

button {
  position: fixed;
  justify-self: center;
  max-width: 100px;
}
</style>
