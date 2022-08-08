<script setup lang="ts">
defineProps<{
  title: string;
}>();
</script>

<template>
  <div class="hero min-h-screen bg-base-200">
    <div class="hero-content text-center">
      <div class="flex flex-col max-w-lg h-screen items-center justify-center">
        <h1 class="text-5xl font-bold pb-5">{{ title }}</h1>
        <div class="form-control pt-5">
          <div class="input-group">
            <input
              type="text"
              placeholder="Type here"
              class="input input-bordered"
            />
            <button class="btn btn-primary btn-square">Go</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
