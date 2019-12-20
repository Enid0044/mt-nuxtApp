<template>
  <div class="m-header">
    <div :gutter="0">
      <el-col :span="7">
        <geo />
      </el-col>
      <el-col :span="3">
        <user />
      </el-col>
      <el-col :span="14">
        <navs />
      </el-col>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import Geo from './geo'
import User from './user'
import Navs from './nav'
export default {
  data() {
    return {

    }
  },
  components: {
    Geo,
    User,
    Navs
  }
}
</script>

<style  lang="scss" >
@import "@/assets/css/public/layout.scss";
@import "@/assets/css/public/header/index.scss";
</style>
