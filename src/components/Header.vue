<template>
  <header>
    <div class="row">
      <div class="col-sm-12">
        <h1 class="title text-center">Quotes Added</h1>
        <div class="progress-container">
          <div
            :class="['progress-bar']"
            :style="{ width: (quoteCount / maxQuotes) * 100 + '%' }"
          >
            <span>{{ quoteCount }}/{{ maxQuotes }}</span>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  props: ["quoteCount", "maxQuotes"]
};
</script>

<style scoped>
.progress-container {
  width: 100%;
  height: 20px;
  background-color: #ddd;
}

.counter {
  font-size: 1rem;
  margin: 0 auto;
  text-align: center;
}
</style>