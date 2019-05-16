<template>
  <div>
    <!-- 热门课程 -->
    <div class="hot-class bra">
      <div class="study-field-title flex">
        <text class="f30 c6">热门微课</text>
        <text class="f22 c6 p10" @click='hotMoreEvent'>更多</text>
      </div>
      <div class="class-content bt" v-for="(item, index) in hotClassList" :key='index' @click='classItemEvent(index)'>
        <div class="flex-dr">
          <div class="class-left flex-sb">
            <text class="f30 c3 lines2">信息安全慢慢谈-----置业担保员工安全手册--置业担保员工安全手册-置业担保员工安全手册</text>
            <text class="f22 c6 info-safety ">信息安全</text>
          </div>
          <div class="class-right">
            <bui-image src="/image/test.jpg" width="220px" height="150px"></bui-image>
          </div>
        </div>
        <div class="flex-dr pt10">
          <div class="flex1 flex-ac">
            <text class="f22 c6">4.5分</text>
          </div>
          <div class="flex1 flex-af pr10">
            <text class="f22 c6">2</text>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        hotClassList: ['', '', '', '']
      }
    },
    methods: {
      // 更多
      hotMoreEvent() {
        this.$alert('更多')
      },
      // 热门微课
      classItemEvent() {
        this.$alert('热门微课')
      }
    }
  }
</script>

<style lang="css" src="../css/common.css"></style>
<style>
  .hot-class {
    background-color: #fff;
  }

  .class-content {
    padding: 20px;
  }

  .class-left {
    width: 480px;
    padding-right: 10px;
  }

  .class-right {
    width: 220px;
  }

  .info-safety {
    width: 120px;
    padding: 0 10px;
    border-radius: 20px;
    background-color: #f2f2f2;
  }
</style>