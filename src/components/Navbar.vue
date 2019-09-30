<template>
  <nav class="navbar navbar-expand-xl py-3 navbar-dark">
    <div class="container">
      <a class="navbar-brand pl-4" href="#">
        <img src="../assets/logo.png" height="40" alt />
      </a>
      <button
        class="navbar-toggler float-right"
        type="button"
        data-toggle="collapse"
        data-target="#navbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="navbar-collapse collapse" id="navbar">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item px-3">
            <a class="nav-link" href="#">Help</a>
          </li>
          <li class="nav-item px-3">
            <a class="nav-link" href="#">Cast out</a>
          </li>
          <li class="nav-item px-3">
            <a class="nav-link" href="#">Upload cast</a>
          </li>
          <li class="nav-item d-none d-md-block">
            <img src="../assets/cover-image.jpg" class="rounded-circle" />
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped lang="scss">
.navbar-collapse {
  background: rgba(20, 33, 50);
  width: 100%;
  img {
    width: 50px;
    height: 50px;
  }
}
</style>
