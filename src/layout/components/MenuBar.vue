<template>
  <div class='menu-bar'>
    <a-menu
      :inline-collapsed="$store.getters.menuCol"
      mode="inline"
      theme="dark"
    >
      <menu-item v-for="(item,index) in list" :key="index" :tree="item">

      </menu-item>

    </a-menu>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'
import { getMenus, getParentMenu } from '@/utils/menus'
import MenuItem from '@/layout/components/menuItem'
import { reactive } from 'vue'

const router = useRouter()
const list = reactive(getMenus(getParentMenu(router.getRoutes())))

</script>
<style lang="scss" scoped>
//   .ant-menu-dark {
//     color: rgba(255, 255, 255, 0.65);
//     background: #000c17 !important;
//     .ant-menu ant-menu-sub ant-menu-inline{
//       color: rgba(255, 255, 255, 0.65);
//     background: #000c17 !important;
//     }
// }
</style>
