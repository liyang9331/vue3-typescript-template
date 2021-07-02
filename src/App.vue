<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import 'bootstrap/dist/css/bootstrap.min.css';
import { defineComponent } from 'vue';
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
const currentUser:UserProps = {
  islogin: true,
  name: 'liyang'
}
const testData: ColumnProps[] = [
  {
    id: 1,
    title: '测试专栏',
    description: 'dsafdsfdsf发送到发送到发送到干豆腐干豆腐',
    avatar: require('@/assets/test.jpeg')
  },
  {
    id: 2,
    title: '测试专栏',
    description: 'dsafdsfdsf发送到发送到发送到干豆腐干豆腐'
    // avatar: require('./assets/test.jpeg')
  },
  {
    id: 3,
    title: '测试专栏',
    description: 'dsafdsfdsf发送到发送到发送到干豆腐干豆腐',
    avatar: require('./assets/test.jpeg')
  },
  {
    id: 4,
    title: '测试专栏',
    description: 'dsafdsfdsf发送到发送到发送到干豆腐干豆腐',
    avatar: require('./assets/test.jpeg')
  }
];
export default defineComponent({
  name: 'App',
  components: {
    ColumnList,
    GlobalHeader
  },
  setup () {
    return {
      list: testData,
      currentUser
    };
  }
});
</script>

<style>
</style>
