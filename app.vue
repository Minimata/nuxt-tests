<script setup>
import { createClient, provideClient } from "@urql/vue";

const client = createClient({
  url: "https://tkwleelnoiqszqxnesgw.nhost.run/v1/graphql",
  fetchOptions: () => {
    const token = getToken();
    return {
      headers: { authorization: token ? `Bearer ${token}` : "" },
    };
  },
});

provideClient(client);
</script>

<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
