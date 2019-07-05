<template>
  <div id="navigation-view">
    <ul>
      <h1>My Vue App</h1>
      <li>
        <router-link :to=" { name: 'usertestimonials' } ">Testimonials</router-link>
      </li>
      <li>
        <router-link :to=" { name: 'contact' } ">Contact</router-link>
      </li>
      <li>
        <router-link :to=" { name: 'about' } ">About</router-link>
      </li>
      <li>
        <router-link :to=" { name: 'home' } ">Home</router-link>
      </li>
    </ul>
  </div>
</template>

<style scoped lang='scss'>
#navigation-view ul {
  padding: 45px;
}

ul h1 {
  position: absolute;
  color: white;
  margin-top: none;
  padding-left: 20px;
  left: 20px;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: lightblue;
  border: 1px black solid;
}

li {
  float: right;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: lightblue;
  text-decoration: underline;
}

.active {
  background-color: lightblue;
}
</style>