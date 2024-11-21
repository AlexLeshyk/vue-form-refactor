<template>
  <div class="card card-w70">
    <template v-if="elements.length">
      <component
          v-for="block in elements"
          v-bind:key="block.id"
          v-bind:is="'block-' + block.type"
          v-bind:property="block.value"
      >
      </component>
    </template>
    <p v-else>Блоков нет</p>
  </div>
</template>

<script>
import BlockTitle from "./block/BlockTitle";
import BlockText from "./block/BlockText";
import BlockSubtitle from "./block/BlockSubtitle";
import BlockAvatar from "./block/BlockAvatar";
export default {
  name: "AppView",
  props: ['elements'],
  components: {
    BlockTitle: BlockTitle,
    BlockText: BlockText,
    BlockSubtitle: BlockSubtitle,
    BlockAvatar: BlockAvatar,
  }
}
</script>

<style scoped>

</style>