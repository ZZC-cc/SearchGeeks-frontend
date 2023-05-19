<template>
  <a-list item-layout="horizontal" :data-source="props.postList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          <template #title>
            <h4>{{ item.title }}</h4>
          </template>
          <template #avatar>
            <a-avatar style="background-color: #87d068">大佬</a-avatar>
          </template>
          <template #description>
            <div style="max-width: 800px">{{ item.content }}</div>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>
<script setup lang="ts">
import gege from "../assets/gege.jpg";
import { withDefaults, defineProps, toRefs } from "vue";

interface Props {
  postList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  postList: () => [],
});
</script>
<style scoped>
.gege {
  width: 200px;
}
</style>
