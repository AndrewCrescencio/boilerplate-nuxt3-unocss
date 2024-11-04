<script setup lang="ts">
const online = useOnline()
</script>

<template>
  <div>
    <Suspense>
      <ClientOnly>
        <section class="mx-auto container">
          <p v-if="online">
            Oi amigo
          </p>
          <p v-else text-gray:80>
            You're offline
          </p>
        </section>
      </ClientOnly>
      <template #fallback>
        <div italic op50>
          <span animate-pulse>Loading...</span>
        </div>
      </template>
    </Suspense>
  </div>
</template>
