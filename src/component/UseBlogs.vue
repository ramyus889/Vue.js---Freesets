<script>
export default {
  name: 'UseIllustrations',
  mounted() {
    document.title = 'Freesets | Blogs';
  }
};
</script>
<script setup>
import axios from 'axios';
import { computed, onMounted, ref } from 'vue';

const illustrations = ref([]);
const searchQuery = ref('');

const url = 'https://79d87a1f9ee388f6.mokky.dev/blogs';
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
  <div class="flex place-content-center">
    <div class="">
      <div class="mt-[31px] flex place-content-center mx-auto">
        <input
          type="text"
          v-model="searchQuery"
          class="w-[300px] p-3 border-2 rounded-xl border-zinc-700"
          placeholder="Search blogs"
        />
      </div>
      <div
        class="grid xl:grid-cols-4 lg:grid-cols-3 sm:grid-cols-2 grid-cols-1 gap-5 px-6 mt-[20px]"
      >
        <div
          v-for="item in filteredUsers"
          :key="item.id"
          data-aos="fade-up"
          :data-aos-delay="item.delay"
          class="rounded-lg group ring-zinc-700 ring-2 hover:ring-[#00a1ff] transition-all"
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
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
