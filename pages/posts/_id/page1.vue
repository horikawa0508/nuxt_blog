<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">title of the post</h1>
      <div class="post-details">
        <div class="post-detail">Last update on XXX</div>
        <div class="post-detail">Written by yuta</div>
      </div>
      <h3><p class="post-content">AxiosでQiitaのAPIから取得</p></h3>
      <div>
      <table class="table">
        <thead class="thead-dark">
          <tr>
            <th>No</th>
            <th>First Name</th>
            <th>Updated at</th>
          </tr>
        </thead>
        <tbody class="axios-list" v-for="(post, idx) in posts" :key="idx">
          <tr>
            <th scope="row">{{idx}}</th>
            <td><a :href="'post.url'" target="_blank" rel="noopener noreferrer">{{ post.title }}</a></td>
            <td>{{ post.updated_at }}</td>
          </tr>
        </tbody>
      </table>
      </div>
    </section>
    <section class="post-feedback">
    <p>Let me message:<a href="mailto:yuta.horikawa@kikagaku.co.jp">yuta.horikawa@kikagaku.co.jp</a></p>
    </section>
  </div>
</template>

<script>
	export default {
		async asyncData({ $axios }) {
			const url = "https://qiita.com/api/v2/items";
      const response = await $axios.$get(url);
      // console.log(response)
			return {
				posts: response
			};
		}
	};
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}

.axios-list {
    list-style: none;
}
</style>