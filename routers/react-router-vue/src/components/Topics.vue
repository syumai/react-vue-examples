<template>
  <div>
    <h2>Topics</h2>
    <ul>
      <li>
        <router-link :to="`${match.url}/rendering`">
          Rendering with Vue
        </router-link>
      </li>
      <li>
        <router-link :to="`${match.url}/components`">
          Components
        </router-link>
      </li>
      <li>
        <router-link :to="`${match.url}/props-v-state`">
          Props v. State
        </router-link>
      </li>
    </ul>

    <route :path="`${match.url}/:topicId`" :component="Topic" />
    <route exact :path="match.url" :render="renderElement" />
  </div>
</template>

<script>
import React from 'react';

import {
  Route,
  Link as RouterLink // Not working with name 'Link'
} from 'react-router-dom';

import Topic from './Topic';

export default {
  props: ['match'],

  data: {
    Topic
  },

  components: {
    Route,
    RouterLink
  },

  methods: {
    renderElement() {
      return <h3>Please select a topic.</h3>;
    }
  }
}

</script>
