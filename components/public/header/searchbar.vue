<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col :span='3' class='left'>
        <img src="//s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png" alt="美团">
      </el-col>
      <el-col :span='6' class='center'>
        <div class="wrapper">
          <el-input placeholder='搜索商家或地点' v-model='search' @focus="fcous" @blur="blur" @input="input"></el-input>
          <button class='el-button el-button-primary'>
            <i class='el-icon-search'></i>
          </button>
          <dl class='hotPlace' v-if='isHotPlace'>
            <dt>热门搜索</dt>
            <dd v-for='(item,index) in HotPlace' :key='index'>{{item}}</dd>
          </dl>
          <dl class="searchList" v-if='isSearchList'>
            <dd v-for="(item,index) in searchList" :key='index'>火锅</dd>
          </dl>
        </div>
        <p class='suggset'>
          <a href="#">故宫博物馆</a>
          <a href="#">故宫博物馆</a>
          <a href="#">故宫博物馆</a>
          <a href="#">故宫博物馆</a>
          <a href="#">故宫博物馆</a>
          <a href="#">故宫博物馆</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link to="/" class='takeout'>美团外卖</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class='movice'>猫眼电影</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class='hotel'>m美团酒店</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class='apartment'>民宿/公寓</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class='business'>商家入驻</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col :span='5' class='right'>
        <ul class="security">
          <li>
            <i class='refund'></i>
            <p class="txt">随时退</p>
          </li>
          <li>
            <i class='refund'></i>
            <p class="txt">过期退</p>
          </li>
          <li>
            <i class='refund'></i>
            <p class="txt">不满意免单</p>
          </li>
        </ul>
      </el-col>
    </el-row>

  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data() {
    return {
      isFocus: false,
      search: '',
      HotPlace: [],
      searchList: [],

    }
  },
  computed: {
    isHotPlace() {
      return this.isFocus && !this.search
    },
    isSearchList() {
      return this.isFocus && this.search
    }
  },
  methods: {
    fcous() {
      this.isFocus = true;
    },
    blur() {
      let self = this;
      setTimeout(function () {
        self.isFocus = false
      }, 200)
    },
    input() {

    }
  },
  components: {


  }
}
</script>

<style  lang="scss" >
</style>
