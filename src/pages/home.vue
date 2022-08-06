<template>
  <div class="md-body">
    <h1>Hello home</h1>
    <p>Edit me</p>
  </div>
</template>

<script lang="ts">
import axios from 'axios'
import { defineComponent } from "vue";

export default defineComponent({
  setup() {
    axios.get('url').then(() => {})
  },
})
</script>