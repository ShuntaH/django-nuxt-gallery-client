<template>
  <header>
    <div class="text-box">
      <h1>Photo-Gallery</h1>
      <p class="mt-3">
        Let's make your gallery stock
      </p>
      <nuxt-link class="btn btn-outline btn-large btn-info" to="/photos">
        photos list
        <span class="ml-2">→</span>
      </nuxt-link>
    </div>
  </header>
</template>
<script>
  export default {
    head () {
      return {
        title: 'Home page'
      }
    }
  }
</script>
<style>
  header {
    min-height: 100vh;
    background-image: linear-gradient(
      to right,
      rgba(0, 0, 0, 0.7),
      rgba(0, 0, 0, 0.2)
    ),
    url("~assets/images/bg.jpg");
    background-position: center;
    background-size: cover;
    position: relative;
  }
  .text-box {
    position: absolute;
    top: 50%;
    left: 10%;
    transform: translateY(-50%);
    color: #fff;
  }
  .text-box h1 {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    font-size: 5rem;
  }
  .text-box p {
    font-size: 2rem;
    font-weight: lighter;
  }
</style>
