<script>
export default {
  async asyncData({$notion}) {
    const blockMap = await $notion.getPageBlocks("ad2346af0894443d8906cf78de4f310f")
    return {blockMap}
  },
  data: () => ({blockMap: null}),
  head: {
    title: "About"
  },
}
</script>


<template>
  <NotionRenderer :block-map="blockMap" full-page prism/>
</template>


<style>
@import "vue-notion/src/styles.css";

.notion-title, .notion-text, .notion-list, .notion-callout-text, p, h1, h2, h3, h4, span {
  @apply dark:text-white;
}

.notion-link {
  @apply dark:hover:bg-red-500;
}
</style>
