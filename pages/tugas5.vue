<template>
  <div>
    <!-- navbar -->
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Tugas Telat</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="/">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/tugas4">Tugas 4</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/tugas5">Tugas 5</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- navbar end -->

    <div>
      <div v-for="(article, index) in articles" :key="index">
        <h2>{{ article.title }}</h2>
        <p>{{ article.content }}</p>
        <img style="width: 300px" :src="article.img" :alt="article.title" />
      </div>
    </div>
  </div>
</template>
  
  <script>
import { articles } from '@/components/data'
export default {
  data() {
    return {
      articles,
    }
  },
}
</script>
<style scoped>
</style>
  