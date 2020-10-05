<template>
  <main class="container mt-5">
    <div class="row">
      <div class="col-12 text-right mb-4">
        <div class="d-flex justify-content-between">
          <h3>育てた水草一覧</h3>
          <nuxt-link to="/waterplants/add" class="btn btn-info">
            水草を追加する
          </nuxt-link>
        </div>
      </div>
      <template v-for="photo in photos">
        <div :key="photo.id" class="col-lg-3 col-md-4 col-sm-6 mb-4">
          <water-plant-card :onDelete="deletePhoto" :photo="photo"></water-plant-card>
        </div>
      </template>
    </div>
  </main>
</template>
<script>

  import PhotosCard from '~/components/PhotosCard.vue'

  export default {
    head () {
      return {
        title: 'Photos list'
      }
    },
    components: {
      PhotosCard
    },
    data () {
      return {
        photos: null
      }
    },
    async asyncData ({ $axios, params}) {
      const photos = await $axios.$get(`/photos/`)
        .catch( (error) => {
          console.error(error)
          return {
            photos: {}
          }
          }
        )
      return {
        photos
      }
    },
    methods: {
      async deletePhoto (photo_id) {
        this.photo = await this.$axios.$delete(`/photos/${photo_id}/`)
      }
    }
  }
</script>
<style scoped>
</style>
