<script setup lang="ts">
import { useQuery, gql } from "@urql/vue";

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
`;

const delay = (n: number) => {
  return new Promise(function (resolve) {
    setTimeout(resolve, n * 1000);
  });
};

const { data, fetching, error } = await useQuery({
  query: GetArticles,
});

// watch([data, fetching, error], () => {
//   if (data.value) {
//     const articles = data.value._helloworld_article;
//     articles.forEach((article: { title: string; author: any }) => {
//       console.log(article.title);
//     });
//   }
// });

const articles = data.value._helloworld_article;
</script>

<template>
  <div>
    <ul>
      <div>
        <div v-for="article in articles" :key="article.id">
          <li>{{ article.title }} {{ article.author.name }}</li>
        </div>
      </div>
    </ul>
  </div>
</template>
