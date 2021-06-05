<template>
  <div
    class="py-8 px-8 max-w-sm mx-auto bg-white rounded-xl shadow-md space-y-2 sm:py-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-6 float-center"
  >
    <div class="text-center space-y-2 sm:text-center">
      <div class="space-y-0.5">
        <p class="text-lg text-black font-semibold">{{ tweet.content }}</p>
      </div>
    </div>
    <button
      class="transition duration-500 ease-in-out  transform hover:-translate-y-1 hover:scale-110 px-4 py-1 text-sm text-purple-600 font-semibold rounded-full border border-purple-200 hover:text-white hover:bg-purple-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-purple-600 focus:ring-offset-2"
      @click="favorite(tweet.id)"
    >
      Favorite
    </button>
  </div>
  <br />
</template>
<script>
export default {
  name: "TweetComponent",
  emits: ["favorite"],

  props: {
    tweet: Object,
  },
  methods: {
    favorite(id) {
      this.$emit("favorite", id);
    },
  },
};
</script>
