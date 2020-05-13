<template>
  <div class="container">
    <MainTitle/>
    <!-- PostPreview -->
    <div class="row mb-2">
      <PostPreview id="1" category="Technique"  day="2020/05/13" title="Axios" previewText="Axiosでpostgetしたデータをtableで表示" thumbnail='@assets/images/01.jpg'/>
      <PostPreview id="2" category="World" day="2020/05/11" title="Mountain" previewText="this is nature!" thumbnail='@assets/images/01.jpg'  />
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
  }
}
</script>

<style >
.jumbotron {
  background-image: url('~assets/images/main.jpg');
}
</style>
