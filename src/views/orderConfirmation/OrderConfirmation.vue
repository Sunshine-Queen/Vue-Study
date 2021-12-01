<template>
    <div class="top">
        <div class="top__header">
            <div class="iconfont top__header_back">&#xe600;</div>
            确认订单
        </div>
        <div class="top__receiver">
            <div class="top__receiver__title">收货地址</div>
            <div class="top__receiver__address">北京理工大学国防科技园2号楼10层</div>
            <div class="top__receiver__address">北京理工大学国防科技园2号楼10层</div>
            <div class="top__receiver__info">
                <span class="top__receiver__info__name">幺妹（先生）</span>
                <span class="top__receiver__info__name">12334422543</span>
            </div>
            <div class=" iconfont top__receiver__enter">&#xe600;</div>
        </div>
    </div>
</template>

<script>
export default{
    name:'OrderConfirmation'
}
</script>

<style lang="scss" scoped>
.top{
    height: 1.96rem;
    background-size:100% 1.59rem;
    background-image:linear-gradient(0deg,rgba(0,145,255,0.00) 4%,#0091FF 50%);
    background-repeat: no-repeat;
}
</style>
