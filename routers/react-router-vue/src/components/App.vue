<template>
  <router>
    <div>
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/topics">Topics</router-link></li>
      </ul>

      <hr/>

      <route exact path="/" :component="Home" />
      <route path="/about" :component="About" />
      <route path="/topics" :component="Topics" />
    </div>
  </router>
</template>

<script>
import React from 'react';
import {
  BrowserRouter as Router,
  Route,
  Link as RouterLink // Not working with name 'Link'
} from 'react-router-dom';

import Home from './Home';
import About from './About';
import Topic from './Topic';
import Topics from './Topics';

export default {
  data: {
    Home,
    About,
    Topics
  },

  components: {
    Router,
    Route,
    RouterLink
  }
};
</script>
