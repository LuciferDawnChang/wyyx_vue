<template>
  <div class="discernGambit">
    <header class="title">
      <h4>十点一刻</h4>
    </header>
    <!-- Swiper -->
    <div class="swiper-container-discernGambit swiper-container-horizontal">
      <div class="swiper-wrapper">
        <a class="swiper-slide"  v-if="tenfifteens"
             v-for="(item,index) in tenfifteens" :key="index" :href="item.url">
          <div class="dGItemHead"><span>—</span>今日话题<span>—</span></div>
          <div class="dGItemTitle">{{item.title}}</div>
          <div class="dGItemDesc">{{item.desc}}</div>
        </a>
      </div>
      <span class="swiper-notification" aria-live="assertive" aria-atomic="true"></span>
    </div>
  </div>
</template>

<script>
  import Swiper from "swiper";
  import {mapState} from "vuex";
  export default {
    computed:{
      ...mapState(["tenfifteens"])
    },
    mounted(){
      this.$store.dispatch("getTenfifteens",()=>{
        new Swiper('.swiper-container-discernGambit', {
          slidesPerView: 'auto',
          spaceBetween: 15,
          loop:true,
          pagination: {
            el: '.swiper-pagination',
            clickable: true,
          },
        });
      });
    }
  }
</script>

<style lang="less" scoped>
  @import "../../common/less/mixins";
  .discernGambit{
    box-sizing: border-box;
    width: 100%;
    height:571/@rem;
    padding: 0 30/@rem 40/@rem;
    margin-bottom: 20/@rem;
    background-color: #fff;
    .title{
      width: 100%;
      height: 120/@rem;
      line-height: 120/@rem;
      font-size: 32/@rem;
      text-align: center;
    }
    .swiper-container-discernGambit {
        display: flex;
        width: 100%;
        height: 100%;
      .swiper-wrapper{
        display: flex;
        flex-wrap: nowrap;
        .swiper-slide {
          font-size: 18px;
          width: 500/@rem;
          height:294/@rem;
          padding: 38/@rem 40/@rem 79/@rem;
          background: url("./images/bg.png") no-repeat;
          -webkit-background-size: 100%;
          background-size: 100%;
          /* Center slide text vertically */
          /*display: -webkit-box;*/
          /*display: -ms-flexbox;*/
          /*display: -webkit-flex;*/
          /*display: flex;*/
          /*flex-direction: column;*/
          /*align-items: center;*/
          .dGItemHead{
            /*padding: 0 8/@rem;*/
            color: #7f7f7f;
            line-height: 30/@rem;
            font-size: 0.20/@rem;
            margin-bottom: 40/@rem;
            span{
              margin: 0 8/@rem;
            }
          }
          .dGItemTitle{
            font-weight: 700;
            margin-bottom: 14/@rem;
            font-size: 36/@rem;
          }
          .dGItemDesc{
            line-height: 1.5;
            font-size: 28/@rem;
          }
        }
      }
    }
  }
</style>
