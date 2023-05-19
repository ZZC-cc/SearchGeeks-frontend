<template>
  <a-list item-layout="horizontal" :data-source="props.userList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          <template #description>
            <p>{{ item.userProfile }}</p>
          </template>
          <template #title>
            <h4>{{ item.userName }}</h4>
          </template>
          <template #avatar>
            <a-avatar style="color: #fff; background-color: #1890ff">{{
              item.userName
            }}</a-avatar>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import gege from "../assets/gege.jpg";
import { withDefaults, defineProps } from "vue";

interface Props {
  userList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  userList: () => [],
});
</script>
<style scoped>
.gege {
  width: 200px;
}
</style>
