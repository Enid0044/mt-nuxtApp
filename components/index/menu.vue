<template>
  <div class="m-menu">
    <dl class='nav'>
      <dt @mouseleave="mouseleave">全部分类</dt>
      <dd v-for="(item,index) in menu" @mouseenter="enter(item.type,index)">
        <i :class='item.type'></i>
        {{item.name}}
        <span class="arrow"></span>
      </dd>
    </dl>
    <div v-if="kind" class="detail" @mouseenter="sover" @mouseleave="sout">
      <template v-for="(item,idx) in menu[nameIndex].child">
        <h4 :key="idx">{{ item.name }}</h4>
        <span v-for="v in item.child" :key="v">{{ v }}</span>
      </template>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">

export default {
  data() {
    return {
      menu: [{
        type: 'food',
        name: '美食',
        child: [{
          title: '美食',
          child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']
        }]
      }, {
        type: 'takeout',
        name: '外卖',
        child: [{
          title: '外卖',
          child: ['美团外卖']
        }]
      }, {
        type: 'hotel',
        name: '酒店',
        child: [{
          title: '酒店星级',
          child: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
        }]
      }],
      _timer: 0,
      kind: null,
      nameIndex: 0,
    }
  },
  computed: {
    // curdetail: function () {
    //   return this.$store.state.home.menu.filter(item => item.type === this.kind)[0]
    // }
  },
  methods: {
    mouseleave() {
      this._timer = setTimeout(() => {
        this.kind = ''
      }, 150)
    },
    enter(name, index) {
      this.kind = name;
      this.nameIndex = index
    },
    sover() {
      clearTimeout(this._timer)
    },
    sout() {
      this.kind = ''
    }
  },
  components: {

  }
}
</script>

<style lang="scss" >
// @import url("../../assets/css/index/index.scss");
</style>
