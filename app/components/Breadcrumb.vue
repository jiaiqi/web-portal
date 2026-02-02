<script setup lang="ts">
interface BreadcrumbItem {
  name: string
  path?: string
}

defineProps<{
  items: BreadcrumbItem[]
}>()
</script>

<template>
  <div class="border-b border-gray-200 bg-gray-50">
    <div class="mx-auto px-4 py-3 max-w-7xl lg:px-8 sm:px-6">
      <nav class="text-sm text-gray-600 flex items-center">
        <NuxtLink to="/" class="transition-colors hover:text-red-700">
          首页
        </NuxtLink>
        <template v-for="(item, index) in items" :key="index">
          <span class="text-gray-400 mx-2">/</span>
          <NuxtLink
            v-if="item.path && index < items.length - 1"
            :to="item.path"
            class="transition-colors hover:text-red-700"
          >
            {{ item.name }}
          </NuxtLink>
          <span v-else :class="{ 'text-red-700 font-medium': index === items.length - 1 }">
            {{ item.name }}
          </span>
        </template>
      </nav>
    </div>
  </div>
</template>
