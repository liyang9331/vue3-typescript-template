<template>
  <nav class="navbar navbar-expand-lg navbar-light nav-reset">
      <a class="navbar-brand" href="#">知乎专栏</a>
      <div v-if="!user.islogin">
          <button type="button" class="btn btn-primary">登录</button>
            <button type="button" class="btn btn-primary">注册</button>
      </div>
      <div v-else>
          <dropdown :title="`你好${user.name}`"></dropdown>
      </div>
  </nav>
</template>
<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Dropdown from '../components/Dropdown.vue'
export interface UserProps {
    islogin:boolean;
    name?:string;
    id?:number;
}
export default defineComponent({
  name: 'GlobalHeader',
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  },
  components: {
    Dropdown
  }
})
</script>
<style scoped>
.nav-reset{
    margin-bottom: 20px;
    background-clip: content-box;
    -webkit-box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
    box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
    background: #F7F8F8;
    padding: 0 16px !important;
    height: 52px !important;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>
