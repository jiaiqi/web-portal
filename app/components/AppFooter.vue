<script setup lang="ts">
// 固定的二维码图案，避免 hydration 不匹配
const qrPattern = [
  true,
  true,
  true,
  true,
  true,
  true,
  false,
  false,
  false,
  true,
  true,
  false,
  true,
  false,
  true,
  true,
  false,
  false,
  false,
  true,
  true,
  true,
  true,
  true,
  true,
]

const linksRow1 = [
  { name: '中国文联', url: '#' },
  { name: '中国作协', url: '#' },
  { name: '中国剧协', url: '#' },
  { name: '中国影协', url: '#' },
  { name: '中国音协', url: '#' },
  { name: '中国美协', url: '#' },
  { name: '中国曲协', url: '#' },
  { name: '中国舞协', url: '#' },
  { name: '中国民协', url: '#' },
]

const linksRow2 = [
  { name: '中国摄协', url: '#' },
  { name: '中国书协', url: '#' },
  { name: '中国杂协', url: '#' },
  { name: '中国视协', url: '#' },
  { name: '中国文学艺术基金会', url: '#' },
]

const bottomLinks = [
  { name: '联系咨询', url: '#' },
  { name: '投诉建议', url: '#' },
  { name: '文艺论坛', url: '#' },
  { name: '职能部门', url: '#' },
  { name: '团体会员', url: '#' },
  { name: '组织机构', url: '#' },
]
</script>

<template>
  <footer class="text-white bg-red-700">
    <!-- Links Section -->
    <div class="mx-auto px-4 py-8 max-w-7xl lg:px-8 sm:px-6">
      <div class="flex flex-col gap-8 justify-between lg:flex-row">
        <!-- Left Links -->
        <div class="flex-1">
          <h3 class="text-lg font-bold mb-4">
            链接
          </h3>
          <div class="space-y-3">
            <div class="text-sm flex flex-wrap gap-x-2 items-center">
              <template v-for="(link, index) in linksRow1" :key="link.name">
                <NuxtLink :to="link.url" class="transition-colors hover:text-yellow-300">
                  {{ link.name }}
                </NuxtLink>
                <span v-if="index < linksRow1.length - 1" class="text-red-400">|</span>
              </template>
            </div>
            <div class="text-sm flex flex-wrap gap-x-2 items-center">
              <template v-for="(link, index) in linksRow2" :key="link.name">
                <NuxtLink :to="link.url" class="transition-colors hover:text-yellow-300">
                  {{ link.name }}
                </NuxtLink>
                <span v-if="index < linksRow2.length - 1" class="text-red-400">|</span>
              </template>
            </div>
          </div>
        </div>

        <!-- Right QR Code -->
        <div class="flex flex-col items-center">
          <div class="mb-2 p-1 rounded-lg bg-white h-24 w-24">
            <div class="rounded bg-gray-200 flex h-full w-full items-center justify-center">
              <div class="gap-0.5 grid grid-cols-5 h-16 w-16">
                <div
                  v-for="(cell, i) in qrPattern"
                  :key="i"
                  class="bg-gray-800"
                  :class="{ 'bg-transparent': !cell }"
                />
              </div>
            </div>
          </div>
          <p class="text-xs text-center">
            中国文艺志愿者微信公众号
          </p>
        </div>
      </div>
    </div>

    <!-- Bottom Section -->
    <div class="py-4 bg-red-800">
      <div class="mx-auto px-4 max-w-7xl lg:px-8 sm:px-6">
        <div class="text-xs text-red-200 text-center space-y-2">
          <p>网站总访问量：103019</p>
          <div class="flex flex-wrap gap-x-4 items-center justify-center">
            <NuxtLink v-for="link in bottomLinks" :key="link.name" :to="link.url" class="transition-colors hover:text-white">
              {{ link.name }}
            </NuxtLink>
          </div>
          <p>工信部ICP备案号 京ICP备14001194号-1 京公网安备11010502025171 中国文艺志愿者协会 版权所有</p>
        </div>
      </div>
    </div>
  </footer>
</template>
