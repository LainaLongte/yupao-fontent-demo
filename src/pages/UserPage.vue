<template>
  <van-cell title="用户名" is-link :value="user?.username" @click="toEdit('username', '用户名', user?.username)"/>
  <van-cell title="用户账号" :value="user?.userAccount" />
  <van-cell title="性别" :value="user?.gender" />
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";
import {onMounted, ref} from "vue";
import myAxios from "../plugins/myAxios";
import {Toast} from "vant";
import {getCurrentUser} from "../services/user";

const user = {
  id: 1,
  username: '鱼皮',
  userAccount: 'dogYupi',
  avatarUrl: 'https://636f-codenav-8grj8px727565176-1256524210.tcb.qcloud.la/img/logo.png',
  gender: '男',
  phone: '123112312',
  email: '12345@qq.com',
  planetCode: '1234',
  createTime: new Date(),
}

// const user = ref();

const router = useRouter();

// onMounted(async () => {
//   user.value = await getCurrentUser();
// })

const toEdit = (editKey: string, editName: string, currentValue: string) => {
  router.push({
    path: '/user/edit',
    query: {
      editKey,
      editName,
      currentValue,
    }
  })
}
</script>

<style scoped>

</style>
