<script setup lang="ts">
const route = useRoute()

const navItems = [
  { name: '首页', path: '/' },
  { name: '协会概况', path: '/about' },
  { name: '要闻动态', path: '/news' },
  { name: '党建工作', path: '/party' },
  { name: '品牌活动', path: '/activities' },
  { name: '表彰激励', path: '/awards' },
  { name: '公告公示', path: '/announcements' },
  { name: '专题', path: '/topics' },
  { name: '全国联动', path: '/cooperation' },
  { name: '智慧平台', path: '/platform' },
]

function isActive(path: string) {
  if (path === '/') {
    return route.path === '/'
  }
  return route.path.startsWith(path)
}
</script>

<template>
  <header class="w-full">
    <!-- Top Logo Section -->
    <div class="bg-white">
      <div class="mx-auto px-4 py-4 max-w-7xl lg:px-8 sm:px-6">
        <div class="flex gap-4 items-center">
          <!-- Logo -->
          <div class="flex gap-3 items-center">
            <div class="rounded-full flex h-16 w-16 items-center justify-center from-red-500 to-red-700 bg-gradient-to-br">
              <div class="rounded-full bg-white flex h-12 w-12 items-center justify-center">
                <div class="rounded-full h-8 w-8 from-yellow-400 to-blue-500 via-red-500 bg-gradient-to-br" />
              </div>
            </div>
            <div class="flex flex-col">
              <h1 class="text-2xl text-gray-800 tracking-wide font-bold">
                中国文艺志愿者
              </h1>
              <p class="text-xs text-gray-500 tracking-wider">
                CHINA LITERARY AND ART VOLUNTEERS
              </p>
              <p class="text-xs text-gray-400">
                中国文学艺术界联合会主管 中国文艺志愿者协会主办
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Navigation Bar -->
    <nav class="bg-red-700">
      <div class="mx-auto px-4 max-w-7xl lg:px-8 sm:px-6">
        <div class="flex h-12 items-center">
          <div class="flex items-center space-x-1">
            <NuxtLink
              v-for="item in navItems"
              :key="item.path"
              :to="item.path"
              class="text-sm text-white font-medium px-5 py-3 transition-all duration-200 hover:bg-red-800"
              :class="{ 'bg-red-800': isActive(item.path) }"
            >
              {{ item.name }}
            </NuxtLink>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>
