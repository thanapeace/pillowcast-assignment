<template>
<body>
  <div id="app">
    <Navbar />
    <Header
      :name="name"
      :tagline="tagline"
      :num_cast="num_cast"
      :num_follower="num_follower"
      :num_following="num_following"
      :status="status"
    />
    <Subnavbar />
    <router-view v-on:handleSubmit="handleSubmit" :status="status" :tagline="tagline" />
  </div>
</body>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Header from "@/components/Header.vue";
import Subnavbar from "@/components/Subnavbar.vue";

export default {
  name: "app",
  components: {
    Navbar,
    Header,
    Subnavbar
  },
  data: function() {
    return {
      name: "",
      tagline: "",
      status: 0,
      num_cast: "33",
      num_follower: "3243",
      num_following: "3444"
    };
  },
  methods: {
    handleSubmit: function(value) {
      this.name = value.name;
      this.sexual = value.sexual;
      this.tagline = value.tagline;
      this.birthdate = value.birthdate;
      this.status = 1;
      console.log(this.profile);
    }
  }
};
</script>


<style lang="scss">
#app {
}
</style>


