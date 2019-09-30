<template>
<div>
  <div class="container pl-4 mt-4 mb-5">
    <div v-if="status == 0">
      <NoData />
    </div>
    <div v-else>
      <HomePage />
    </div>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
import Subnavbar from "@/components/Subnavbar.vue";
import HomePage from "@/components/HomePage.vue";
import NoData from "@/components/NoData.vue";

export default {
  name: "home",
  components: {
    Subnavbar,
    HomePage,
    NoData
  },
  props: {
    status: Number,
    tagline: String,
  },
  data:function(){
    return{
      status: 0
    }
  }
};
</script>

<style scoped lang="scss">
h1 {
  letter-spacing: 1px;
  font-weight: bold;
}
</style>