<template>
  <div class="container pl-4 mt-4 mb-5">
    <h1 class="mb-4">About you</h1>
    <Form v-on:handleSubmit="handleSubmit" />
  </div>
</template>

<script>
// @ is an alias to /src
import Form from "@/components/Form.vue";

export default {
  name: "about",
  components: {
    Form
  },
  data:function(){
        return {
      profile:Object,
      name: "", 
      tagline: "", 
    }
  },
  methods: {
    handleSubmit:function(value) {
      this.profile = value
      this.name=value.name
      this.tagline=value.tagline
      this.$emit("handleSubmit", this.profile);
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
