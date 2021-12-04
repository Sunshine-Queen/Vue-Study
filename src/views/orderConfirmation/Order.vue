<template>
    <div class="order">
        <div class="order__price">实付金额 <b>{{calculations.price}}</b></div>
        <div class="order__btn">提交订单</div>
    </div>
    <div class="mask">
        <div class="mask__content">
            <h3 class="mask__content__title">确认要离开收银台?</h3>
            <p class="mask__content__desc">请尽快完成支付，否则将被取消</p>
            <div class="mask__content__btns">
                <div class="mask__content__btn">取消订单</div>
                <div class="mask__content__btn">确认支付</div>
            </div>
        </div>
    </div>
</template>

<script>
import {useRoute} from 'vue-router'
import {useCommonCartEffect} from '../../effects/cartEffects'
export default{
    name:'Order',
    setup(){
        const route = useRoute()
        const shopId=route.params.id
        const {calculations } = useCommonCartEffect(shopId)
        return {calculations}
    }
}
</script>

<style lang="scss">
@import '../../style/viriables.scss';
.order{
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    display:flex;
    height:.49rem;
    line-height:.49rem;
    background:$bgColor;
    &__price{
        flex:1;
        text-indent: .24rem;
        font-size:.14rem;
        color:$content-font-color;
    }
    &__btn{
        width:.98rem;
        background:#4FB0F9;
        color:$bgColor;
        text-align: center;
        font-size: .14rem;
    }
}
.mask{
    z-index:1;
    position: absolute;
    left:0;
    right:0;
    bottom:0;
    top:0;
    background:rgba(0,0,0,0.50);
    &__content{
        position: absolute;
        top:50%;
        left:50%;
        transform: translate(-50%,-50%);
        width:3rem;
        height: 1.56rem;
        background:#FFF;
        border-radius: .04rem;
        text-align: center;
        &__title{
            margin: .24rem 0 0 0;
            line-height: .26rem;
            font-size: .18rem;
            color:#333;
        }
        &__desc{
            margin-top:.08rem 0 0 0;
            font-size: .14rem;
            color:#666;
        }
        &__btns{
            display: flex;
            margin:.24rem .58rem ;
        }
        &__btn{
            
        }
    }
}
</style> 
