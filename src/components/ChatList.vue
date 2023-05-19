<template>
  <a-list item-layout="horizontal" :data-source="props.chatList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          <template #description>
            <p>{{ item.content }}</p>
          </template>
          <template #title>
            <h4>ChatGPT</h4>
          </template>
          <template #avatar>
            <a-avatar :src="chatGPT">ChatGPT</a-avatar>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from "vue";
import chatGPT from "../assets/chatGPT.png";

interface Props {
  chatList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  chatList: () => [],
});
</script>
<style scoped>
.chatGPT {
  width: 200px;
}
</style>
