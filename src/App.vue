<template>
  <div>
    @{{ user.username }} with {{ followers }} followers
    <button @click="followUser">follow the dude</button>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
  },
  data() {
    return {
      followers: 0,
      user: {
        username: "rajanmodi30",
        firstName: "rajan",
        lastName: "modi",
        email: "rajanmodi30@gmail.com",
        isAdmin: true,
      },
    };
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },
  mounted() {
    this.followUser();
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (newFollowerCount > oldFollowerCount) {
        console.log("you gained a follower ", newFollowerCount);
      }
      if (newFollowerCount > 100) {
        alert(`more then ${newFollowerCount}  follow you dawgg`);
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  text-align: center;
}
</style>
