<template>
  <div class="footer">
    <p>Copyright © Abdullah Zeidan 2019</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<style scoped lang="scss">
p {
  float: right;
}

.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  background-color: lightblue;
  color: black;
  text-align: center;
  padding-right: 40px;
  font-weight: bold;
  border: 1px black solid;
  padding: 25px;
}
</style>
