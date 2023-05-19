<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, column: 4 }"
    :data-source="props.pictureList"
  >
    <template #renderItem="{ item }">
      <a-list-item>
        <a-card hoverabl>
          <template #cover>
            <img alt="example" class="gege" :src="item.url" />
          </template>
          <a-card-meta :title="item.title" />
        </a-card>
      </a-list-item>
    </template>
  </a-list>
</template>
<script setup lang="ts">
import { withDefaults, defineProps, toRefs } from "vue";
import gege from "@/assets/gege.jpg";

interface Props {
  pictureList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  pictureList: () => [],
});
</script>
<style scoped>
.gege {
  width: 160px;
  height: 130px;
}
</style>
