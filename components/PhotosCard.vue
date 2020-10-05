<template>
  <div class="card water-plant-card">
    <img :src="photo.picture" class="card-img-top">
    <div class="card-body">
      <h5 class="card-title">
        {{ photo.name }}
      </h5>
      <div class="action-buttons">
        <nuxt-link :to="`/photos/${photo.id}/`" class="btn btn-sm btn-success">
          詳細
        </nuxt-link>
        <nuxt-link :to="`/photos/${photo.id}/edit/`" class="btn btn-sm btn-primary">
          編集
        </nuxt-link>
        <button @click="onDelete(photo.id)" class="btn btn-sm btn-danger">
          削除
        </button>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['photo', 'onDelete']
  }
</script>
<style>
  .water-plant-card {
    box-shadow: 0 1rem 1.5rem rgba(0,0,0,.6);
  }
</style>
