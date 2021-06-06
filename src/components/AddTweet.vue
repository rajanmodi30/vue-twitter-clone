<template>
  <div
    class="py-8 px-8 max-w-sm mx-auto bg-white rounded-xl shadow-md space-y-2 sm:py-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-6 float-center"
  >
    <form @submit.prevent="submitTweet">
      <label>Add Tweet {{ characterCount }} / 180</label>
      <textarea
        v-model="tweetTextArea"
        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
        type="text"
      ></textarea>

      <button
        type="submit"
        class="float-center bg-transparent hover:bg-purple-500 text-purple-500 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
      >
        Tweet
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTweet",
  emits: "submitTweet",
  data() {
    return {
      tweetTextArea: "",
    };
  },
  methods: {
    submitTweet() {
      if (this.tweetTextArea) {
        this.$emit("submitForm", this.tweetTextArea);
        this.tweetTextArea = "";
      }
    },
  },
  computed: {
    characterCount() {
      return this.tweetTextArea.length;
    },
  },
};
</script>
