<template>
  <div>
    <h1>Your upload</h1>
    <div class="row mt-4">
      <div v-for="video in video" :key="video.index" class="col-sm-4">
        <div class="card">
          <div class="card-img-top embed-responsive embed-responsive-16by9">
            <iframe
              class="embed-responsive-item"
              src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0"
              allowfullscreen
            ></iframe>
          </div>
          <div class="card-img-overlay">
            <a id="submit" class="gradient-button float-left">Category name</a>
          </div>
          <div class="card-body">
            <h5 class="card-title">{{video.title}}</h5>
            <p class="card-text">creator name</p>
            <p class="card-text">
              <small class="text-muted">Last updated 3 mins ago</small>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  data: function() {
    return {
      video: [{ title: "video 1" }, { title: "video 2" }, { title: "video 3" }]
    };
  }
};
</script>

<style scoped lang="scss">
.gradient-button {
  opacity: 1;
}
.card-img-top {
  height: 300px;
}
.card {
  border: none;
  background: transparent;
}

.card-body {
  padding: 20px 0px 10px 0px;
}
</style>
