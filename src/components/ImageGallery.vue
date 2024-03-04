<template>
  <div
    class="w-full grow overflow-hidden bg-orange-100 md:flex md:justify-center"
  >
    <div class="m-auto grid gap-4 px-4 py-6">
      <div class="flex flex-col-reverse gap-4 md:flex-row md:items-center">
        <div class="order-2 md:order-1">
          <img
            src="https://p.sda1.dev/16/6f16e2779878073ad543e8734e6ec6b6/04f0cf62fb5a2132dae85a5fe170eb7f95991995.jpg"
            alt="Photo"
            class="aspect-video cursor-pointer overflow-hidden rounded-lg border object-cover"
            @click="goVideo()"
          />
        </div>
        <div class="order-1 grid gap-2 md:order-2">
          <img
            src="https://p.sda1.dev/16/f3b02f680ac1c316f1bb0e302119c167/c41f334789d118d98340bf655f29cc4b95991995.jpg"
            alt="Photo"
            class="aspect-video cursor-pointer overflow-hidden rounded-lg border object-cover"
            @click="goVideo()"
          />
        </div>
      </div>
      <span class="text-center text-gray-500">
        距BangDream国服实装MyGO!!!!!还有：
        <span class="text-2xl font-bold">
          {{ time.days }} 天 {{ time.hours }} 时 {{ time.minutes }} 分
          {{ time.seconds }} 秒 ！
        </span>
      </span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
defineOptions({
  name: "ImageGallery",
});

const goVideo = () => {
  location.href = "https://www.bilibili.com/video/BV13r421H7Fa";
};

// 自动计算当前时间和北京时间2024年4月10日下午一点的时间差，并且每秒更新
const time = ref({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0,
});
const countDown = () => {
  const targetTime = new Date("2024-04-10T13:00:00+08:00").getTime();
  const currentTime = new Date().getTime();
  const timeDiff = targetTime - currentTime;
  time.value = {
    days: Math.floor(timeDiff / (1000 * 60 * 60 * 24)),
    hours: Math.floor((timeDiff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
    minutes: Math.floor((timeDiff % (1000 * 60 * 60)) / (1000 * 60)),
    seconds: Math.floor((timeDiff % (1000 * 60)) / 1000),
  };
};
countDown();
setInterval(countDown, 1000);
</script>

