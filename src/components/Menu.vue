<template>
  <div class="navbar">
    <div class="container">
      <a href="#" class="navbar-brand" v-on:click="toggle">{{title}}</a>
      <ul class="nav navbar-nav pull-right">
        <li>
          <a href="#">Log in</a>
        </li>
        <li>
          <a href="#">Sign up</a>
        </li>
      </ul>
      <ul class="nav navbar-nav">
        <li>
          <a href="#">Home</a>
        </li>
        <li>
          <a href="#">Browse</a>
        </li>
        <li>
          <a href="#">Contribute</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "menu",
  props: {
    title: String
  },
  data() {
    return {
      collapsed: true
    };
  },
  methods: {
    toggle() {
      this.collapsed = !this.collapsed;
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
