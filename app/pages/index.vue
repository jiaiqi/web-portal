<script setup lang="ts">
const carouselSlides = [
  {
    title: '深入学习贯彻习近平文化思想',
    image: 'https://picsum.photos/800/400?random=1',
    link: '/news/1',
  },
  {
    title: '中国文艺志愿者协会第三次全国代表大会',
    image: 'https://picsum.photos/800/400?random=2',
    link: '/news/2',
  },
  {
    title: '文艺志愿服务走进基层',
    image: 'https://picsum.photos/800/400?random=3',
    link: '/news/3',
  },
]

const newsItems = [
  {
    id: 1,
    title: '习近平总书记在中国文联十一大、中国作协十大开幕式上的重要讲话',
    date: '2024-01-15',
    link: '/news/1',
    image: 'https://picsum.photos/200/120?random=4',
  },
  {
    id: 2,
    title: '中国文艺志愿者协会组织开展"送欢乐下基层"慰问演出活动',
    date: '2024-01-14',
    link: '/news/2',
    image: 'https://picsum.photos/200/120?random=5',
  },
  {
    id: 3,
    title: '文艺志愿者走进乡村振兴一线，用艺术助力乡村文化建设',
    date: '2024-01-13',
    link: '/news/3',
    image: 'https://picsum.photos/200/120?random=6',
  },
  {
    id: 4,
    title: '"我们的中国梦"文化进万家活动在全国各地蓬勃开展',
    date: '2024-01-12',
    link: '/news/4',
    image: 'https://picsum.photos/200/120?random=7',
  },
  {
    id: 5,
    title: '新时代文明实践文艺志愿服务项目模式试点工作推进会召开',
    date: '2024-01-11',
    link: '/news/5',
    image: 'https://picsum.photos/200/120?random=8',
  },
]

const localNewsItems = [
  {
    id: 1,
    title: '北京市文联组织开展文艺志愿服务活动',
    date: '2024-01-15',
    link: '/news/local/1',
  },
  {
    id: 2,
    title: '上海市文艺志愿者走进社区慰问演出',
    date: '2024-01-14',
    link: '/news/local/2',
  },
  {
    id: 3,
    title: '广东省文联举办文艺志愿服务培训班',
    date: '2024-01-13',
    link: '/news/local/3',
  },
  {
    id: 4,
    title: '浙江省文艺志愿者开展送温暖活动',
    date: '2024-01-12',
    link: '/news/local/4',
  },
]

const quickLinks = [
  { name: '会员登录', url: '/login' },
  { name: '活动报名', url: '/activities/register' },
  { name: '志愿者注册', url: '/volunteer/register' },
  { name: '资料下载', url: '/downloads' },
]
</script>

<template>
  <div>
    <!-- Hero Section -->
    <div class="mx-auto px-4 py-6 max-w-7xl lg:px-8 sm:px-6">
      <div class="gap-6 grid grid-cols-1 lg:grid-cols-3">
        <!-- Carousel -->
        <div class="lg:col-span-2">
          <NewsCarousel :slides="carouselSlides" />
        </div>
        <!-- Side Banner -->
        <div class="space-y-4">
          <div class="text-white p-6 rounded-lg flex h-36 items-center justify-center from-red-700 to-red-600 bg-gradient-to-r">
            <div class="text-center">
              <h3 class="text-lg font-bold mb-2">
                百花迎春
              </h3>
              <p class="text-sm opacity-90">
                中国文学艺术界春节大联欢
              </p>
            </div>
          </div>
          <div class="text-white p-6 rounded-lg flex h-36 items-center justify-center from-amber-600 to-amber-500 bg-gradient-to-r">
            <div class="text-center">
              <h3 class="text-lg font-bold mb-2">
                文艺进万家
              </h3>
              <p class="text-sm opacity-90">
                健康你我他
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- News Section -->
    <div class="mx-auto px-4 py-6 max-w-7xl lg:px-8 sm:px-6">
      <div class="gap-6 grid grid-cols-1 lg:grid-cols-3">
        <!-- Main News -->
        <div class="space-y-6 lg:col-span-2">
          <!-- Featured Banner -->
          <div class="text-white p-6 rounded-lg from-red-800 to-red-600 bg-gradient-to-r">
            <h2 class="text-xl font-bold mb-2">
              深入学习贯彻党的二十届四中全会精神
            </h2>
            <p class="text-sm opacity-90">
              全面贯彻落实习近平新时代中国特色社会主义思想
            </p>
          </div>

          <!-- News List -->
          <NewsList title="要闻" :items="newsItems" more-link="/news" />
        </div>

        <!-- Sidebar -->
        <div class="space-y-6">
          <NewsList title="基层动态" :items="localNewsItems" more-link="/news/local" />

          <!-- Quick Links -->
          <div class="p-4 rounded-lg bg-white">
            <div class="mb-4 flex gap-2 items-center">
              <span class="rounded bg-red-700 h-5 w-1" />
              <h2 class="text-lg text-gray-800 font-bold">
                快捷入口
              </h2>
            </div>
            <div class="gap-3 grid grid-cols-2">
              <NuxtLink
                v-for="link in quickLinks"
                :key="link.name"
                :to="link.url"
                class="text-sm text-gray-700 px-4 py-3 rounded-lg bg-gray-50 flex transition-colors items-center justify-center hover:text-red-700 hover:bg-red-50"
              >
                {{ link.name }}
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
