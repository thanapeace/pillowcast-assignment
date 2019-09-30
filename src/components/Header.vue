<template>
  <div class="jumbotron">
    <div class="container">
      <div class="card">
        <div class="row no-gutters">
          <div class="col-md-auto text-center">
            <img class="rounded-circle" src="../assets/cover-image.jpg" />
          </div>
          <div class="col-auto mx-4 mt-4 d-none d-md-block">
            <div class="card-block px-2">
              <h1 v-if="status == 0" class="card-title">Empty profile (@empty)</h1>
              <h1 v-else class="card-title">{{name}} (@{{tagline}})</h1>
              <p class="lead sub-title">This is pillowcast assignment</p>
              <h1 class="lead">
                {{formatNumber(num_cast)}} Casts
                ● {{formatNumber(num_follower)}} Followers
                ● {{formatNumber(num_following)}} Following
              </h1>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    name: String,
    tagline: String,
    num_cast: String,
    num_follower: String,
    num_following: String,
    status: Number
  },

  data: function() {
    return {
      name: "",
      tagline: "",
      num_cast: "",
      num_follower: "",
      num_following: "",
      status: 0
    };
  },

  methods: {
    formatNumber: function(num) {
      return String(num.toString().replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,"));
    }
  }
};
</script>

<style scoped lang="scss">
.card {
  background: transparent;
  border: transparent;
}
.jumbotron {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("../assets/cover-image.jpg") no-repeat center center;
  background-size: cover;
  letter-spacing: 1px;
  img {
    width: 200px;
  }
}

.card {
  filter: blur(0) !important;
  z-index: 10;
}

.sub-title {
  font-size: 20px;
}
</style>
