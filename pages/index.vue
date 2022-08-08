<template>
  <div>
    <BasicInput title="Welcome">
      <Suspense>
        <Asynchronous> </Asynchronous>

        <template #fallback>
          <span>Loading...</span>
        </template>
      </Suspense>
    </BasicInput>
  </div>
</template>
