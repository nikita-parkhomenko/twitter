<template>
  <div class="user-profile">

    <div class="user-profile__user-panel">

      <h2 class="user-profile__username">@{{ user.userName }}</h2>
      <p v-if="user.isAdmin" class="user-profile__admin-badge">Admin</p>

      <div class="user-profile__follower-count">
        <strong>Followers: {{ followers }}</strong>
      </div>

    </div>

    <div class="user-profile__tweets-wrapper">
      <TweetItem 
        v-for="tweet in user.tweets" 
        :key="tweet.id" 
        :userName="user.userName" 
        :tweet="tweet" 
        @favourite="addToFavourites" 
      />
    </div>

  </div>
</template>

<script>
import TweetItem from './TweetItem';

export default {
  name: 'UserProfile',
  components: { TweetItem },
  data() {
    return {
      followers: 100,
      user: {
        userName: '_Nekit_Park',
        firstName: 'Nikita',
        lastName: 'Parkhomenko',
        email: 'nikita.parkhom@gmail.com',
        id: 1,
        isAdmin: false,
        tweets: [
          { id: 1, content: 'Thanks Tesla Team for great work on deliveries! For new owners, we super appreciate accommodating us on delivery timing! Definitely one of our toughest quarters in global logistics.' },
          { id: 2, content: 'Completed a full duration test fire of the Raptor Vacuum engine at SpaceX’s rocket development facility in McGregor, Texas'},
        ]
      }
    }
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  },
  methods: {
    addFolowers() {
      this.followers++
    },
    addToFavourites(id) {
      console.log(`Tweet #${id} added to favourites List`);
    }
  },
  mounted() {
    console.log('The page is Mounted!')
  }
}
</script>

<style scoped>
.user-profile {
  display: flex;
  justify-content: start;
  width: vw;
  padding: 50px 5%;
}

.user-profile__user-panel {
  display: flex;
  flex-direction: column;
  width: 20%;
  padding: 20px;
  margin-right: 50px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid #dfe3e8;
}

.user-profile__follower-count {
  margin-top: 10px;
}

.user-profile__admin-badge {
  background-color: rgb(129, 45, 255);
  color: white;
  padding: 5px 10px;
  border-radius: 5px;
  margin-right: auto;
}
</style>