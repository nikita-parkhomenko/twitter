<template>
  <div class="tweet" @click="favouriteTweet(tweet.id)">

    <div class="tweet__wrapper">
      <h5 class="tweet__user">
        @{{ userName }}
      </h5>

      <p class="tweet__content">
        {{ tweet.content }}
      </p>
    </div>

  </div>
</template>

<script>
  export default {
    name: 'TweetItem',
    props: {
      userName: {
        type: String,
        required: true
      },
      tweet: {
        type: Object,
        required: true
      }
    },
    methods: {
      favouriteTweet(id) {
        this.$emit('favourite', id)
      }
    }
  }
</script>

<style scoped>
  .tweet {
    width: 60%;
    padding: 20px;
    background-color: white;
    border-radius: 8px;
    border: 1px solid #dfe3e8;
    box-sizing: border-box;
    cursor: pointer;
    transition: 0.4s all;
    margin-bottom: 20px;
  }

  .tweet:hover {
    transform: scale(1.05);
    background-color: #d9eeff;
  }

  .tweet__user {
    font-weight: bold;
  }
</style>

