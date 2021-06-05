<template>
  <div
    class="py-8 px-8 max-w-sm mx-auto bg-white rounded-xl shadow-md space-y-2 sm:py-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-6 float-center"
  >
    <div class="text-center space-y-2 sm:text-center">
      <div class="space-y-0.5">
        <p class="text-lg text-black font-semibold">{{ tweet.content }}</p>
      </div>
    </div>
  </div>
  <br>
</template>
<script>
export default {
  name: "TweetComponent",
  props: {
    tweet: Object,
  },
};
</script>
