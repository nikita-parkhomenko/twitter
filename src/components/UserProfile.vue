<template>
  <div class="user-profile">

    <div class="user-profile__user-panel">

      <h1 class="user-profile__username">@{{ user.userName }}</h1>
      <p v-if="user.isAdmin" class="user-profile__admin-badge">Admin</p>

      <div class="user-profile__follower-count">
        <strong>Followers: {{ followers }}</strong>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: 'UserProfile',
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
    }
  },
  mounted() {
    console.log('The page is Mounted!')
  }
}
</script>

<style scoped>
.user-profile {
  display: grid;
  grid-template-columns: 1fr 3fr;
  width: 100%;
  padding: 50px 5%;
}

.user-profile__user-panel {
  display: flex;
  flex-direction: column;
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