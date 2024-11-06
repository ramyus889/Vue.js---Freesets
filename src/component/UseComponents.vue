<script>
export default {
  name: 'UseIllustrations',
  mounted() {
    document.title = 'Freesets | Components';
  }
};
</script>
<script setup>
import axios from 'axios';
import { computed, onMounted, ref } from 'vue';

const illustrations = ref([]);
const searchQuery = ref('');

const url = 'https://79d87a1f9ee388f6.mokky.dev/components';
const fetchIllustrations = async () => {
  try {
    const res = await axios.get(url);
    illustrations.value = res.data;
  } catch (error) {
    console.error(error);
  }
};

const filteredUsers = computed(() => {
  return illustrations.value.filter((item) => {
    return item.title.toLowerCase().includes(searchQuery.value.toLowerCase());
  });
});

onMounted(() => {
  fetchIllustrations();
});
</script>

<template>
  <div
    class="sticky top-0 left-0 right-0 z-20 flex justify-center mx-auto mt-6 border-t-2 border-zinc-600"
  >
    <a
      href="#"
      type="button"
      class="relative flex gap-2 items-center px-10 py-1.5 bg-[#21c95f] rounded-b-[20px]"
    >
      <img src="/headIcon/components.svg" alt="" class="w-6" />
      <h2 class="text-[17px] font-semibold">
        Components <span class="text-[15px] font-semibold">(42)</span>
      </h2>
    </a>
  </div>
  <div class="flex place-content-center">
    <div class="">
      <div class="mt-[31px] flex place-content-center mx-auto">
        <input
          type="text"
          v-model="searchQuery"
          class="w-[300px] p-3 border-2 rounded-xl border-zinc-700"
          placeholder="Search components"
        />
      </div>
      <div class="grid xl:grid-cols-4 lg:grid-cols-3 sm:grid-cols-2 grid-cols-1 gap-5 mt-[20px]">
        <div
          v-for="item in filteredUsers"
          :key="item.id"
          data-aos="fade-up"
          :data-aos-delay="item.delay"
          class="rounded-lg group ring-zinc-700 ring-2 hover:ring-[#21c95f] transition-all"
        >
          <a :href="item.link" target="_blank" class="">
            <img
              :src="item.image"
              alt=""
              class="object-cover rounded-t-lg aspect-video group-hover:scale-[1.01] transition-transform -z-10"
            />
          </a>
          <div
            class="flex flex-wrap items-center justify-between w-full p-5 rounded-b-lg bg-zinc-800"
          >
            <a
              :href="item.link"
              target="_blank"
              class="sm:text-[18px] text-[16px] font-semibold hover:underline"
              >{{ item.title }}</a
            >
            <a
              :href="item.tagLink"
              target="_blank"
              class="bg-blue-700 transition-all hover:scale-105 px-2 py-1 font-semibold rounded-md text-[13px] tracking-wide"
            >
              {{ item.tag }}</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
