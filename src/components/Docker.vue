<template >
    <div class="docker">
    <div  v-for="(item,index) in  dockerList"
    :class="{'docker__item':true,'docker__item--active':index === currentIndex}"
    :key="item.icon"
    >
    <router-link :to='item.to'>
      <div class="iconfont" v-html="item.icon"/>
      <div class="docker_title" >{{item.text}}</div>
    </router-link>
    </div>
  </div>
</template>

<script>
export default{
    name:'Docker',
    props:['currentIndex'],
    setup(){
        const dockerList=[
            {icon:'&#xe674;',text:'首页',to:{name:'Home'}},
            {icon:'&#xe603;',text:'购物车',to:{name:'CartList'}},
            {icon:'&#xe60c;',text:'订单',to:{name:'OrderList'}},
            {icon:'&#xe660;',text:'我的',to:{name:'Home'}},
        ];
        return { dockerList }  
    }
}
</script>

<style lang="scss" scoped>
@import '../style/viriables.scss';
 
.docker {
  display: flex;
  box-sizing: border-box;
  position: absolute;
  padding: 0 .18rem;
  left: 0;
  bottom: 0;
  width: 100%;
  height: .49rem;
  border-top: .01rem solid $content-bgColor;
  color: $content-font-color;
;
  &__item {
    flex: 1;
    text-align: center;
    .iconfont {
      margin: .07rem 0 .02rem 0;
      font-size: .18rem;
    }
    a{
      color: $content-font-color;
      text-decoration: none;
    }
    &--active {
      a{
        color: #1FA4FC;
      }
    }
  }
  &__title {
    font-size: .2rem;
    transform: scale(.5, .5);
    transform-origin: center top;
  }
}
</style>