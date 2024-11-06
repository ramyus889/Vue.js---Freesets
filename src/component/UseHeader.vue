<script setup>
import { routeUrl } from '../router/routes.js';

const items = [
  {
    id: 1,
    icon: '/headIcon/home.svg',
    to: `${routeUrl[0].path}`,
    bgColor: '!bg-white !border-none'
  },
  {
    id: 2,
    title: 'Icons',
    icon: '/headIcon/icons.svg',
    to: `${routeUrl[1].path}`,
    bgColor: '!bg-[#2b6dff]  !border-none !text-white'
  },
  {
    id: 3,
    title: 'Illustrations',
    icon: '/headIcon/illustrations.svg',
    to: `${routeUrl[2].path}`,
    bgColor: '!bg-[#20c928]  !border-none !text-white'
  },
  {
    id: 4,
    title: 'Photos',
    icon: '/headIcon/photos.svg',
    to: `${routeUrl[3].path}`,
    bgColor: '!bg-[#d41cf1]  !border-none !text-white'
  },
  {
    id: 5,
    title: 'Videos',
    icon: '/headIcon/videos.svg',
    to: `${routeUrl[4].path}`,
    bgColor: '!bg-[#ef2350]  !border-none !text-white'
  },
  {
    id: 6,
    title: 'Colors',
    icon: '/headIcon/colors.svg',
    to: `${routeUrl[5].path}`,
    bgColor: '!bg-[#ff36a2]  !border-none !text-white'
  },
  {
    id: 7,
    title: 'Backgrounds',
    icon: '/headIcon/backgrounds.svg',
    to: `${routeUrl[6].path}`,
    bgColor: '!bg-[#5345f7]  !border-none !text-white'
  },
  {
    id: 8,
    title: 'Typography',
    icon: '/headIcon/typography.svg',
    to: `${routeUrl[7].path}`,
    bgColor: '!bg-[#ffaa1b]  !border-none !text-white'
  },
  {
    id: 9,
    title: '3D',
    icon: '/headIcon/3d.svg',
    to: `${routeUrl[8].path}`,
    bgColor: '!bg-[#8935ff]  !border-none !text-white'
  },
  {
    id: 10,
    title: 'Libraries',
    icon: '/headIcon/libraries.svg',
    to: `${routeUrl[9].path}`,
    bgColor: '!bg-[#ff006e]  !border-none !text-white'
  },
  {
    id: 11,
    title: 'Blogs',
    icon: '/headIcon/blogs.svg',
    to: `${routeUrl[10].path}`,
    bgColor: '!bg-[#00a1ff]  !border-none !text-white'
  },
  {
    id: 12,
    title: 'Tools',
    icon: '/headIcon/tools.svg',
    to: `${routeUrl[11].path}`,
    bgColor: '!bg-[#f97316]  !border-none !text-white'
  },
  {
    id: 13,
    title: 'Inspirations',
    icon: '/headIcon/inspirations.svg',
    to: `${routeUrl[12].path}`,
    bgColor: '!bg-[#6366f1]  !border-none !text-white'
  },
  {
    id: 14,
    title: 'Components',
    icon: '/headIcon/components.svg',
    to: `${routeUrl[13].path}`,
    bgColor: '!bg-[#21c95f]  !border-none !text-white'
  }
];
</script>

<template>
  <div class="flex flex-wrap gap-2 place-content-center">
    <div v-for="item in items" :key="item.id" class="2xl:min-w-[55rem]">
      <RouterLink
        :to="item.to"
        :class="item.bgColor"
        class="px-4 py-1.5 flex items-center w-full justify-center gap-2 flex-grow rounded-md"
        ><img :src="item.icon" class="w-[23px]" alt="" /> {{ item.title }}</RouterLink
      >
    </div>
  </div>
</template>
