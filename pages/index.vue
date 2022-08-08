<script setup lang="ts">
import { useClientHandle } from "@urql/vue";

const urql = useClientHandle();

const { data, fetching, error } = await urql.useQuery({
  query: `{
    _helloworld_article {
        title
        author {
            name
        }
    }
  }`,
});
</script>

<template>
  <BasicInput title="Welcome" />
  <ul>
    <div v-for="article in data" :key="article.title">
      <li>{{ article.title }} {{ article.author }}</li>
    </div>
  </ul>
</template>
