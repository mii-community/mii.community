<template>
  <ul class="md:max-w-screen-sm space-y-4">
    <li
      v-for="(work, index) in works"
      :key="index"
      class="hover:opacity-50 transition duration-200"
    >
      <a
        target="_blank"
        rel="noopener noreferrer"
        :href="work.url"
        class="h-32 w-full flex rounded-lg border border-gray-800 shadow-md"
      >
        <div class="force-32 border-r border-gray-800">
          <img
            class="rounded-lg p-1"
            :src="require(`~/assets/img/works/${work.img}`)"
            :alt="work.alt"
          />
        </div>
        <div class="w-full relative">
          <h2 class="h-8 leading-8 font-bold text-center">
            {{ work.title }}
          </h2>
          <div
            class="h-16 text-sm px-2 flex justify-center items-center whitespace-normal"
          >
            {{ work.description }}
          </div>
          <div>
            <h3
              class="h-8 text-gray-700 text-sm flex justify-end right-align pr-2"
            >
              by {{ work.author }}
            </h3>
          </div>
        </div>
      </a>
    </li>
  </ul>
</template>

<script lang="ts">
interface Work {
  img: string
  title: string
  description: string
  author: string
  url: string
  alt: string
}

const works: Work[] = [
  {
    img: '15puzzle.png',
    title: '15Puzzle',
    description: '最高のUXを求め続ける15パズルのウェブアプリ。',
    author: 'HiraginoYuki',
    url: 'https://15-puzzle.app',
    alt: 'HiraginoYukiが作った15パズルのウェブアプリのアイコン',
  },
  {
    img: 'gensogacha.png',
    title: '元素ガチャ',
    description: 'シビアな確率設定がリアルな体感をもたらします。',
    author: 'Hirosuke',
    url: 'https://genso-gacha.com',
    alt: 'Hirosukeが作ったガチャのウェブアプリのアイコン',
  },
]

export default {
  data() {
    return { works }
  },
}
</script>
