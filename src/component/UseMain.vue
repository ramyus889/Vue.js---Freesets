<script setup>
import { routeUrl } from '@/router/routes';
import Button from 'primevue/button';
import { ref } from 'vue';

const items = [
  {
    id: 1,
    icon: 'pi pi-home',
    to: `${routeUrl[0].path}`,
    bgColor: ' !bg-white  !border-none'
  },
  {
    id: 2,
    icon: 'pi pi-objects-column',
    to: `${routeUrl[1].path}`,
    bgColor: '!bg-[#2b6dff]  !border-none !text-white'
  },
  {
    id: 3,
    icon: 'pi pi-pencil',
    to: `${routeUrl[2].path}`,
    bgColor: '!bg-[#20c928]  !border-none !text-white'
  },
  {
    id: 4,
    icon: 'pi pi-camera',
    to: `${routeUrl[3].path}`,
    bgColor: '!bg-[#d41cf1]  !border-none !text-white'
  },
  {
    id: 5,
    icon: 'pi pi-video',
    to: `${routeUrl[4].path}`,
    bgColor: '!bg-[#ef2350]  !border-none !text-white'
  },
  {
    id: 6,
    icon: 'pi pi-palette',
    to: `${routeUrl[5].path}`,
    bgColor: '!bg-[#ff36a2]  !border-none !text-white'
  },
  {
    id: 7,
    icon: 'pi pi-image',
    to: `${routeUrl[6].path}`,
    bgColor: '!bg-[#5345f7]  !border-none !text-white'
  },
  {
    id: 8,
    icon: 'pi pi-language',
    to: `${routeUrl[7].path}`,
    bgColor: '!bg-[#ffaa1b]  !border-none !text-white'
  },
  {
    id: 9,
    icon: 'pi pi-box',
    to: `${routeUrl[8].path}`,
    bgColor: '!bg-[#8935ff]  !border-none !text-white'
  },
  {
    id: 10,
    icon: 'pi pi-book',
    to: `${routeUrl[9].path}`,
    bgColor: '!bg-[#ff006e]  !border-none !text-white'
  },
  {
    id: 11,
    icon: 'pi pi-receipt',
    to: `${routeUrl[10].path}`,
    bgColor: '!bg-[#00a1ff]  !border-none !text-white'
  },
  {
    id: 12,
    icon: 'pi pi-hammer',
    to: `${routeUrl[11].path}`,
    bgColor: '!bg-[#f97316]  !border-none !text-white'
  },
  {
    id: 13,
    icon: 'pi pi-lightbulb',
    to: `${routeUrl[12].path}`,
    bgColor: '!bg-[#6366f1]  !border-none !text-white'
  },
  {
    id: 14,
    icon: 'pi pi-arrows-alt',
    to: `${routeUrl[13].path}`,
    bgColor: '!bg-[#21c95f]  !border-none !text-white'
  }
];

const playState = ref('playing');
</script>
<template>
  <div class="flex place-content-center">
    <div class="">
      <div
        class="px-6 text-white font-semibold lg:text-[128px] text-[64px] lg:mt-[250px] sm:mt-[150px] mt-[100px] text-center"
      >
        Freesets
      </div>
      <div class="">
        <Vue3Marquee
          :direction="'reverse'"
          :pause-on-hover="true"
          @on-pause="playState = 'paused'"
          @on-resume="playState = 'playing'"
          class="lg:max-w-[55rem] sm:max-w-[40rem] max-w-[20rem] px-5 py-2 items-center"
        >
          <Button
            v-for="item in items"
            :key="item.id"
            class="mx-5"
            size="medium"
            :to="item.to"
            as="router-link"
            :icon="item.icon"
            :label="item.title"
            :class="item.bgColor"
          />
        </Vue3Marquee>
      </div>
    </div>
  </div>
</template>
