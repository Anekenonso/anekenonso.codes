<template>
  <Layout>
    <br>
    <g-link to="/" class="link">  &larr; Go Back</g-link>
    <div class="post-title">
      <h1>{{$page.post.title}}</h1>
      <p class="post-date"> {{ $page.post.date}} | {{ $page.post.tags}} | {{$page.post.timeToRead}} min read</p>
    </div>
    <div class="post-content">
      <p v-html="$page.post.content" />
    </div>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
   post: post (path: $path) {
    id
    title
    content
    date (format: "D MMMM YYYY")
    timeToRead
  }
}
</page-query>

<style>

.post-title {
  text-align: center;
  text-emphasis: none;
  font-size: 10px;
  line-height: 2px;
  padding: 1em 0;
  font-family: 'Stylish';
}

.post-date {
  font-size: 16px;
  font-weight: 400;
}

.post-tags {
  font-size: 15px;
  font-weight: 400;
}

.post-content {
  font-size: 20px;
}
</style>