<template>
  <div class="container">
    <MainTitle/>
    <!-- PostPreview -->
    <div class="row mb-2">
      <PostPreview id="1" category="Technique"  day="2020/05/13" title="GET" previewText="AxiosでGETしたデータをテーブルで表示" :thumbnail='img1'/>
      <PostPreview id="2" category="Technique" day="2020/05/14" title="POST" previewText="AxiosでPOSTしたデータをテーブルで表示" :thumbnail='img2'/>
    </div>
    <!-- end PostPreview -->

    <hr>

    <main role="main" class="container">
      <div class="row">
        <SampleBlog/>
        <Asider />
      </div><!-- /.row -->
    </main><!-- /.container -->
  </div>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview.vue'
import SampleBlog from '@/components/SampleBlog.vue'
import Asider from '@/components/Asider.vue'
import MainTitle from '@/components/MainTitle.vue'

export default {
  components: {
    PostPreview,
    SampleBlog,
    Asider,
    MainTitle,
  },
  data() {
    return {
        img1:require('@/assets/images/01.jpg'),
        img2:require('@/assets/images/02.jpg'),
    }
  }
}
</script>

<style >
.jumbotron {
  background-image: url('~assets/images/main.jpg');
}
</style>
