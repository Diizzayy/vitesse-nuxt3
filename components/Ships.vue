<template>
  <div class="w-64 container mx-auto shadow bg-light-50 rounded">
    <h3 class="text-xl text-black font-semibold underline">
      Ships
    </h3>

    <div class="p-4 flex flex-col gap-5">
      <p v-for="entry of data?.ships" :key="entry.id" class="">
        {{ entry.name }}
      </p>
    </div>
  </div>
</template>

<script lang="ts" setup>
const { data } = useAsyncData('ships', () => GqlShips({ limit: 3 }))
</script>
