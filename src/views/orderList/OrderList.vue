<template >
    <div class="wrapper">
        <div class="title">我的订单</div>
        <div class="orders">
            <div class="order">
                <div class="order__title">
                    沃尔玛
                    <span class="order__status">已取消</span>
                </div>
                <div class="order__content">
                    <div class="order__content__imgs">
                        <img class="order__content__img" src="http://www.dell-lee.com/imgs/vue3/tomato.png" >
                        <img class="order__content__img" src="http://www.dell-lee.com/imgs/vue3/tomato.png" >
                        <img class="order__content__img" src="http://www.dell-lee.com/imgs/vue3/tomato.png" >
                        <img class="order__content__img" src="http://www.dell-lee.com/imgs/vue3/tomato.png" >
                    </div>
                    <div class="order__content__info">
                        <div class="order__content__price">￥36.88</div>
                        <div class="order__content__count">共2件</div>
                    </div>
                </div>
            </div>
        </div>
  </div>
  <Docker :currentIndex="2"/>
</template>

<script>
import {reactive} from 'vue'
import {get} from '../../utils/request'
import Docker from '../../components/Docker.vue'
const useOrderListEffect = () =>{
    const data=reactive({list:[]})
    const getNearbyList=async()=>{
           const result =await get('/api/order')  
           console.log(result,'--result--')      
            //if(result?.errno===0&&result?.data?.length){
               //nearbyList.value=result.data
            //}
        }
        get
    return { data }
}

export default{
    name:'OrderList',
    components:{Docker},
    setup(){
        return {}
    }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

.wrapper{
  overflow-y:auto ;
  position: absolute;
  left:0;
  top:0;
  bottom:.5rem;
  right:0;
  background: rgb(248, 248, 248);
}
.title{
    line-height: .44rem;
    background: $bgColor;
    font-size:.16rem;
    color:$content-font-color;
    text-align: center;
}
.order{
    margin:.16rem .18rem;
    padding:.16rem;
    background: $bgColor;
    &__title{
        margin-bottom: .16rem;
        line-height: .22rem;
        font-size: .16rem;
        color:$content-font-color;
    }
    &__status{
        float: right;
        font-size: .14rem;
        color:$light-fontColor;
    }
    &__content{
        display: flex;
        &__imgs{
            flex:1;
        }
        &__img{
            width:.4rem;
            height:.4rem;
            margin-right: .12rem;
        }
        &__info{
            width:.7rem;
        }
        &__price{
            margin-bottom: .04rem;
            line-height: .2rem;
            font-size: .14rem;
            color:$hightlight-fontColor;
            text-align: right;
        }
        &__count{
            line-height: .14rem;
            font-size: .12rem;
            color:$content-font-color;
            text-align: right;
        }
    }
}
</style>
