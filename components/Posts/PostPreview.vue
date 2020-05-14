<template>
      <div class="col-md-6">
        
          <div class="row no-gutters border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
            <div class="col p-4 d-flex flex-column position-static">
              <strong class="d-inline-block mb-2 text-primary">{{ category }}</strong>
              <h3 class="mb-0">{{ title }}</h3>
              <div class="mb-1 text-muted">{{ day }}</div>
              <p class="card-text mb-auto">{{ previewText }}</p>
              <nuxt-link :to="'/posts/page' + id">Continue reading</nuxt-link>
            </div>
            <div class="col-auto d-none d-lg-block">
              <img class="bd-placeholder-img" width="200" height="250" :src="thumbnail" preserveAspectRatio="xMidYMid slice" focusable="false" role="img" aria-label="Placeholder: Thumbnail"><title>Placeholder</title><rect width="100%" height="100%" fill="#55595c"></rect>
            </div>
          </div>
      </div>
</template>

<script>
export default {
  name: 'PostPreview',
  props: {
    id: {
      type: String,
      required: true
    },
    category:{
      type: String,
      ewquired: true
    },
    title: {
      type: String,
      required: true,
    },
    day: {
      type: String,
      required: true,
    },
    previewText: {
      type: String,
      required:true,
    },
    thumbnail: {
      type: String,
      required: true
    }
  }
}
</script>