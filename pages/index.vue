<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>
<script>
  import axios from 'axios'
  export default {
    async asyncData() {
      const { data } = await axios.get(
// your-service-id部分は⾃分のサービスidに置き換えてください
        'https://bumptakayuki.microcms.io/api/v1/blog',
        {
// your-api-key部分は⾃分のapi-keyに置き換えてください
          headers: { 'X-API-KEY': '5383df4d-d380-47c8-aaa7-cd7e6bda8a5d' }
        }
      )
      return data
    }
  }
</script>
