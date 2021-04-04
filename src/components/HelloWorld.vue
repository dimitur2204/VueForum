<template>
  <main>
    <h1>Welcome to the forum</h1>
    <div v-for="thread in threads" :key="thread.id" class="col-large push-top">
      <h1>{{ thread.title }}</h1>

      <div class="post-list">
        <div v-for="postId in thread.posts" :key="postId" class="post">
          <div class="user-info">
            <a href="profile.html#profile-details" class="user-name">{{
              users[posts[postId].userId].name
            }}</a>

            <a href="#">
              <img
                class="avatar-large"
                :src="users[posts[postId].userId].avatar"
                alt=""
              />
            </a>

            <p class="desktop-only text-small">
              {{ Object.keys(users[posts[postId].userId].posts).length }} posts
            </p>

            <p class="desktop-only text-small">
              {{ Object.keys(users[posts[postId].userId].posts).length }}
              threads
            </p>

            <span class="online desktop-only">online</span>
          </div>

          <div class="post-content">
            <div>
              <p>
                {{ posts[postId].text }}
              </p>
            </div>
            <a
              href="#"
              style="margin-left: auto;"
              class="link-unstyled"
              title="Make a change"
              ><i class="fa fa-pencil"></i
            ></a>
          </div>

          <div class="post-date text-faded">
            {{ posts[postId].publishedAt }}
          </div>
        </div>
      </div>
    </div>
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
