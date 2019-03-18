<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
      <router-link tag="a" class="navbar-brand" to="/" exact>Deliveroo clone</router-link>
      <b-navbar-toggle target="nav_collapse"/>
      <b-collapse is-nav id="nav_collapse" class="justify-content-end">
        <!-- <div class="collapse navbar-collapse justify-content-end">
          <ul class="navbar-nav">
            <li v-if="username">
              <a href="#" class="nav-link">Hello {{ username }}</a>
            </li>
            <li v-if="username">
              <a href="/" class="nav-link" @click="logout">Logout</a>
            </li>
            <li v-if="!username">
              <router-link v-if="!username" tag="a" class="nav-link" to="/signin" exact>Signin</router-link>
            </li>
            <li v-if="!username">
              <router-link v-if="!username" tag="a" class="nav-link" to="/signup" exact>Signup</router-link>
            </li>
          </ul>
        </div>-->
        <!-- <b-navbar-nav>
          <b-nav-item v-if="username" href="#">Hello {{ username }}</b-nav-item>
          <b-nav-item v-if="username" href="/" @click="logout">Logout</b-nav-item>
          <b-nav-item v-if="!username" href="/signin">Signin</b-nav-item>
          <b-nav-item v-if="!username" href="/signup">Signup</b-nav-item>
        </b-navbar-nav>-->
        <b-navbar-nav>
          <b-nav-item v-if="username">
            <a href="#" class="nav-link">Hello {{ username }}</a>
          </b-nav-item>
          <b-nav-item v-if="username">
            <a href="/" class="nav-link" @click="logout">Logout</a>
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
      logout: "auth/logout"
    })
  }
};
</script>