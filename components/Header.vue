<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
      <router-link tag="a" class="navbar-brand" to="/" exact>Deliveroo</router-link>
      <b-navbar-toggle target="nav_collapse"/>
      <b-collapse is-nav id="nav_collapse" class="justify-content-end">
        <b-navbar-nav>
          <b-nav-item v-if="username">
            <a href="#" class="nav-link">Hello {{ username }}</a>
          </b-nav-item>
          <b-nav-item v-if="username" to="/">
            <a class="nav-link" @click="logout();emptyCart()">Logout</a>
          </b-nav-item>
          <b-nav-item v-if="!username">
            <router-link v-if="!username" tag="a" class="nav-link" to="/signin" exact>Signin</router-link>
          </b-nav-item>
          <b-nav-item v-if="!username">
            <router-link v-if="!username" tag="a" class="nav-link" to="/signup" exact>Signup</router-link>
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </div>
  </nav>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  computed: {
    username() {
      return this.$store.getters["auth/username"];
    }
  },
  methods: {
    ...mapMutations({
      logout: "auth/logout",
      emptyCart: "cart/emptyList"
    })
  }
};
</script>