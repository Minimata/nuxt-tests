<template>
  <div>
    <button @click="reload">Reload page</button>
    <BasicInput title="Welcome">
      <Suspense>
        <Asynchronous :time="0"> </Asynchronous>
        <template #fallback>
          <span>Loading...</span>
        </template>
      </Suspense>
    </BasicInput>
  </div>
</template>

<script>
export default {
  methods: {
    reload() {
      window.location.reload();
    },
  },
};
</script>
