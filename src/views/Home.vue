<template>
  <div class="home">
    <div class="image">
      <h1>Welcome to Sneakerland</h1>
      <img src="../assets/main.jpg">
    </div>
    <div class="container">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style>
.home h1 {
  text-align: center;
  margin-top: 75px;
}
.home {
  display: flex;
}

.image {
  width: 100%;
}

img {
  padding: 75px;
}
.container {
  display: block;
  box-sizing: border-box;
  padding: 75px;
}
.image .container {
  vertical-align: middle;
}

p {
  font-size: 20px;
  text-align: left;
}
</style>
