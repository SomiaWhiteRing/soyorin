<template>
  <div class="flex justify-center gap-4">
    <span class="text-sm text-gray-500">友链？：</span>
    <a
      v-for="link in links"
      :key="link.url"
      :href="link.url"
      class="text-sm text-orange-400"
      >{{ link.name }}</a
    >
    <span class="text-sm text-gray-500">
      提交或推荐友链和建议请联系
      <a href="mailto:anonsoyo@soyorin.com" class="text-orange-400">
        anonsoyo@soyorin.com
      </a>
      ！
    </span>
  </div>
</template>

<script setup lang="ts">
defineOptions({
  name: "FooterLink",
});

interface Link {
  name: string;
  url: string;
}

const links: Link[] = [
  {
    name: "anontokyo.com",
    url: "https://www.anontokyo.com/",
  },
  {
    name: "oblivionis.com",
    url: "https://www.oblivionis.com",
  },
  {
    name: "看mygo看的",
    url: "https://mygo.shatranj.space/",
  },
];
</script>

