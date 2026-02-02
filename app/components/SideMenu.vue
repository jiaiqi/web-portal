<script setup lang="ts">
defineProps<{
  title: string
  menuItems: MenuItem[]
  basePath: string
}>()

const route = useRoute()

interface MenuItem {
  name: string
  path: string
}

function isActive(path: string) {
  return route.path === path
}
</script>

<template>
  <div class="bg-white w-48">
    <div class="mb-4 pl-3 border-l-4 border-red-700">
      <h2 class="text-lg text-gray-800 font-bold">
        {{ title }}
      </h2>
    </div>
    <nav class="space-y-1">
      <NuxtLink
        v-for="item in menuItems"
        :key="item.path"
        :to="item.path"
        class="text-sm px-4 py-3 border-b border-gray-100 block transition-all duration-200"
        :class="isActive(item.path)
          ? 'bg-red-700 text-white'
          : 'text-gray-700 hover:bg-red-50 hover:text-red-700'
        "
      >
        {{ item.name }}
      </NuxtLink>
    </nav>
  </div>
</template>
