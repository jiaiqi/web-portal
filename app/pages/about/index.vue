<script setup lang="ts">
const menuItems = [
  { name: '协会概况', path: '/about' },
  { name: '协会章程', path: '/about/charter' },
  { name: '协会领导', path: '/about/leaders' },
  { name: '理事会', path: '/about/council' },
  { name: '会员工作条例', path: '/about/regulations' },
]
</script>

<template>
  <div>
    <Breadcrumb :items="[{ name: '协会概况', path: '/about' }, { name: '列表页' }]" />

    <div class="mx-auto px-4 py-8 max-w-7xl lg:px-8 sm:px-6">
      <div class="flex gap-8">
        <!-- Side Menu -->
        <SideMenu
          title="协会概况"
          base-path="/about"
          :menu-items="menuItems"
        />

        <!-- Content -->
        <div class="flex-1">
          <div class="p-8 rounded-lg bg-white">
            <!-- 标题区域 -->
            <div class="mb-6">
              <h1 class="text-xl text-gray-900 font-bold mb-3">
                协会概况
              </h1>
              <div class="h-1 w-16 bg-[#cc0000]" />
            </div>

            <!-- 内容区域 -->
            <div class="text-sm text-gray-700 leading-relaxed max-w-none prose prose-gray">
              <p class="mb-4 text-justify">
                中国文艺志愿者协会（China Literary and Art Volunteers' Association，CLAVA），2013年5月23日在北京成立，现任主席是殷秀梅。中国文艺志愿者协会是在中国文联党组领导下，由民政部指导的，由文艺志愿者和文艺志愿服务组织以及关心支持文艺志愿服务的相关单位自愿组成，按照章程开展活动的全国性、联合性、非营利性社会团体，是党和政府联系广大文艺志愿者的桥梁和纽带，是繁荣发展社会主义文艺事业、建设社会主义文化强国的重要力量。中国文艺志愿者协会是中国文学艺术界联合会的团体会员。
              </p>
            </div>

            <!-- 底部分隔线和导航 -->
            <div class="mt-8 pt-6 border-t border-gray-200">
              <div class="flex flex-wrap items-center justify-center gap-2 text-sm">
                <NuxtLink to="/about" class="text-[#cc0000] hover:underline px-2">
                  协会简介
                </NuxtLink>
                <span class="text-gray-300">|</span>
                <NuxtLink to="/about/organization" class="text-[#cc0000] hover:underline px-2">
                  组织机构
                </NuxtLink>
                <span class="text-gray-300">|</span>
                <NuxtLink to="/about/council" class="text-[#cc0000] hover:underline px-2">
                  理事会
                </NuxtLink>
                <span class="text-gray-300">|</span>
                <NuxtLink to="/about/system" class="text-[#cc0000] hover:underline px-2">
                  制度建设
                </NuxtLink>
              </div>

              <!-- logo下载按钮 -->
              <div class="mt-6 flex justify-center">
                <a
                  href="/logo-download"
                  class="inline-flex items-center gap-2 px-6 py-2 bg-[#cc0000] text-white text-sm rounded hover:bg-[#aa0000] transition-colors"
                >
                  <span>logo下载</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
