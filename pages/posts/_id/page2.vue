<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">POSTしたデータをテーブル表示</h1>
      <div class="post-details">
        <div class="post-detail">Last update on XXX</div>
        <div class="post-detail">Written by yuta</div>
      </div>
      <p class="post-content">POSTしたデータを表示</p>
    </section>
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th>No</th>
          <th>Title</th>
          <th>Body</th>
        </tr>
      </thead>
      <tbody class="axios-list">
        <tr>
          <th scope="row">{{items.UserId}}</th>
          <td>{{ items.title }}</td>
          <td>{{ items.body }}</td>
        </tr>
      </tbody>
    </table>
    <section class="post-feedback">
    <p>Let me message:<a href="mailto:yuta.horikawa@kikagaku.co.jp">yuta.horikawa@kikagaku.co.jp</a></p>
    </section>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  async asyncData() {
    const url = 'https://jsonplaceholder.typicode.com/posts'
    const perms = {
      'UserId':1,
      'title': 'POSTで表示',
      'body': 'POST・GETマスター！',
      }
    const {data} = await axios.post(url, perms)
    // console.log(data)
      return{
        items: data
      }
    }
}
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
</style>