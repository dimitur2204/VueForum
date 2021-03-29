<template>
  <main>
    <h1>Welcome to the forum</h1>
  </main>
</template>

<script>
import sourceData from "@/data.json";

export default {
  name: "HelloWorld",
  data() {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    };
  }
};
</script>
