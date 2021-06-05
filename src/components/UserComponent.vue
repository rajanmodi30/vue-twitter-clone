<template>
  <div>
    <div
      class="py-8 px-8 max-w-sm mx-auto bg-white rounded-xl shadow-md space-y-2 sm:py-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-6"
    >
      <img
        class="block mx-auto h-24 rounded-full sm:mx-0 sm:flex-shrink-0"
        :src="user.image"
        alt="Woman's Face"
      />
      <div class="text-center space-y-2 sm:text-left">
        <div class="space-y-0.5">
          <p class="text-lg text-black font-semibold">@{{ user.username }}</p>
          <p class="text-gray-500 font-medium">{{ followers }} followers</p>
        </div>
        <button
          class="px-4 py-1 text-sm text-purple-600 font-semibold rounded-full border border-purple-200 hover:text-white hover:bg-purple-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-purple-600 focus:ring-offset-2"
          @click="followUser"
        >
          Follow
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserComponent",

  data() {
    return {
      followers: 0,
      user: {
        username: "rajanmodi30",
        firstName: "rajan",
        lastName: "modi",
        email: "rajanmodi30@gmail.com",
        isAdmin: true,
        image:
          "https://images.unsplash.com/photo-1604200213928-ba3cf4fc8436?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80",
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
