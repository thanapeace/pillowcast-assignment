<template>
  <div class="container ">
    <nav class="navbar navbar-default navbar-expand-lg py-0">
      <ul class="navbar-nav mr-auto">
        <div class="nav-item">
          <router-link class="nav-link px-5" @click="active = 'home'" :class="{active: active == 'home' }" to="/">Home</router-link>
        </div>
        <div class="nav-item">
          <router-link class="nav-link px-5" @click="active = 'about'" :class="{active: active == 'about' }" to="/about">About</router-link>
        </div>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Subnavbar"
  
};
</script>

<style scoped lang="scss">

.navbar .navbar-nav {
  margin-top: -10px;
  margin-bottom: 0px;
  width: 100%;
  border-bottom: 1.5px solid rgba(69, 80, 93);
}

.nav-item {
  text-align: center;
}

.nav-link {
  font-size: 25px;
  color: rgba(69, 80, 93);
  border-bottom: 5px solid transparent;
  &:hover {
    border-bottom: 5px solid rgba(255, 205, 3);
    color: rgba(255, 205, 3);
    transition: .5s;
  }
  &:active {
    border-bottom: 5px solid rgba(255, 205, 3);
    color: rgba(255, 205, 3);
  }
}
</style>
