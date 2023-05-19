<template>
  <div class="index-page">
    <a-input-search
      v-model:value="searchText"
      placeholder="请输入搜索内容..."
      enter-button="聚合搜索"
      size="large"
      @search="onSearch"
    />
    <MyDivider />
    <a-tabs v-model:activeKey="activeKey" @change="onTabChange">
      <a-tab-pane key="post" tab="文章">
        <post-list :post-list="postList" />
      </a-tab-pane>
      <a-tab-pane key="picture" tab="图片">
        <picture-list :picture-list="pictureList" />
      </a-tab-pane>
      <a-tab-pane key="user" tab="用户">
        <user-list :user-list="userList" />
      </a-tab-pane>
      <a-tab-pane key="chat" tab="ChatGPT">
        <chat-list :chat-list="chatList" />
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script setup lang="ts">
import { computed, ref, watchEffect } from "vue";
import PostList from "@/components/PostList.vue";
import PictureList from "@/components/PictureList.vue";
import UserList from "@/components/UserList.vue";
import ChatList from "@/components/ChatList.vue";
import MyDivider from "@/components/MyDivider.vue";
import { useRoute, useRouter } from "vue-router";
import myAxios from "@/plugins/myAxios";
import { message } from "ant-design-vue";

const postList = ref([]);

const userList = ref([]);

const pictureList = ref([]);

const chatList = ref([]);

const router = useRouter();
const route = useRoute();
const activeKey = route.params.category;

const initSearchParams = {
  type: activeKey,
  text: "",
  pageSize: 15,
  pageNum: 1,
};

const searchText = ref(route.query.text || "");

/**
 * 加载数据
 * @param params
 */
const loadDataOld = (params: any) => {
  const postQuery = {
    ...params,
    searchText: params.text,
  };
  myAxios.post("post/list/page/vo", postQuery).then((res: any) => {
    postList.value = res.records;
  });
  const userQuery = {
    ...params,
    userName: params.text,
  };
  myAxios.post("user/list/page/vo", userQuery).then((res: any) => {
    userList.value = res.records;
  });
  const pictureQuery = {
    ...params,
    searchText: params.text,
  };
  myAxios.post("picture/list/page/vo", pictureQuery).then((res: any) => {
    pictureList.value = res.records;
  });
};

/**
 * 加载聚合数据
 * @param params
 */
const loadAllData = (params: any) => {
  const query = {
    ...params,
    searchText: params.text,
  };
  myAxios.post("search/all", query).then((res: any) => {
    postList.value = res.postList;
    userList.value = res.userList;
    pictureList.value = res.pictureList;
    chatList.value = res.chatList;
  });
};
/**
 * 加载单类数据
 * @param params
 */
const loadData = (params: any) => {
  const { type } = params;
  if (!type) {
    message.error("类别为空");
    return;
  }
  const query = {
    ...params,
    searchText: params.text,
  };
  myAxios.post("search/all", query).then((res: any) => {
    if (type === "post") {
      postList.value = res.dataList;
    } else if (type === "user") {
      userList.value = res.dataList;
    } else if (type === "picture") {
      pictureList.value = res.dataList;
    } else if (type === "chat") {
      chatList.value = res.dataList;
    }
  });
};

const searchParams = ref(initSearchParams);

watchEffect(() => {
  searchParams.value = {
    ...initSearchParams,
    text: route.query.text,
    type: route.params.category,
  } as any;
  loadData(searchParams.value);
});

const onSearch = (value: string) => {
  router.push({
    query: {
      ...searchParams.value,
      text: value,
    },
  });
  loadData(searchParams.value);
};
const onTabChange = (key: string) => {
  router.push({
    path: `/${key}`,
    query: searchParams.value,
  });
};
</script>
<style scoped>
.chat-list .ant-list-item-meta-title {
  display: none;
}

.chat-list .ant-list-item-meta-description {
  color: #fff;
  background-color: #007bff;
  border-color: #007bff;
}
</style>
