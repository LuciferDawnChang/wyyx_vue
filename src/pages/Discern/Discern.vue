<!--
  识物组件
-->
<template>
  <div class="discern">
    <!--头部样式-->
    <HeaderTop/>
    <!--轮播图-->
    <DiscernHits/>
    <!--横向滑动-->
    <DiscernScroll/>
    <!--推荐-->
    <DiscernRecommend/>
    <!--十点一刻-->
    <DiscernGambit/>


    <div>

    </div>
  </div>
</template>

<script>
  import HeaderTop from "../../components/HeaderTop/HeaderTop.vue";
  import DiscernHits from "../../components/DiscernHits/DiscernHits.vue";
  import DiscernScroll from "../../components/DiscernScroll/DiscernScroll.vue";
  import DiscernRecommend from "../../components/DiscernRecommend/DiscernRecommend.vue";
  import DiscernGambit from "../../components/DiscernGambit/DiscernGambit.vue";
  export default {
    components:{
      HeaderTop,
      DiscernHits,
      DiscernScroll,
      DiscernRecommend,
      DiscernGambit,
    }
  }
</script>

<style lang="less" scoped>
  @import "../../common/less/mixins";
  .discern{
    padding-top: 87/@rem;
    padding-bottom: 99/@rem;
    width: 100%;
    overflow: hidden;
  }
</style>
