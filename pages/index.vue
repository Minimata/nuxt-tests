<script setup lang="ts">
import { useQuery, gql } from '@urql/vue';

const GetArticles = gql`
query GetArticles {
  _helloworld_article {
    author {
      name
    }
    title
    id
  }
}
`

const { data, fetching, error } = useQuery({
  query: GetArticles,
});

watch([data, fetching, error], () => {
  if (data.value) {
    const articles = data.value._helloworld_article
    articles.forEach((article: { title: string, author: any }) => {
      console.log(article.title)
    });
  }
  console.log(data.value)
})

</script>

<template>
  <div>
    <BasicInput title="Welcome">
      <span>start</span>
      <div v-if="data">
        <div v-if="data.value">
          <ul>
            <div v-for="article in data.value" :key="article.id">
              <li>{{ article.title }} {{ article.author }}</li>
            </div>
          </ul>
        </div>
      </div>
      <span>end</span>
    </BasicInput>

  </div>
</template>
