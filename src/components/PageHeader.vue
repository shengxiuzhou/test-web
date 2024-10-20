<template>
    <div class="header-container">
        <swiper
            :navigation="{
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev'
            }"
            :modules="[Autoplay,Navigation]"
            :autoplay="{delay:3000}"
            ref="mySwiper"
        >
            <swiper-slide v-for="(image, index) in banners" :key="index">
                <el-image :src="image" class="image"></el-image>
            </swiper-slide>
        </swiper>
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
        <div class="menu-container">
            <el-row type="flex" justify="space-around">
                <el-col :span="7">
                    <img class="header-image" src="https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20230424/f668ed8d81dd4fb1b6541d7c532f77ba.png" alt="">
                </el-col>
                <el-col :span="12"> 
                    <el-menu 
                        :default-active="aciveIndex"
                        :class="showPhone? 'hidden-menu': 'show-menu'"
                        mode="horizontal"
                        :ellipsis = "false"
                        >
                        <el-menu-item index="0">首页</el-menu-item>
                        <el-menu-item index="1">新闻</el-menu-item>
                        <el-menu-item index="2">展馆</el-menu-item>
                        <el-menu-item index="3">展商</el-menu-item>
                        <el-menu-item index="4">展品</el-menu-item>
                    </el-menu>
                </el-col>
            </el-row>
        </div>
    </div>
</template>


<script setup>
    import {ref, onMounted} from 'vue'
    import {Swiper, SwiperSlide} from 'swiper/vue'
    import 'swiper/swiper-bundle.css'
    import {Autoplay,Navigation} from 'Swiper/modules'
    const mySwiper = ref(null);
    const banners = ['https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20240512/67646adb13b245bcbee1336d3a8495fc.png', 'https://www.cnci.net.cn/resource/templateRes/201612/13/126338/126338/simg04.png'];
    onMounted(() => {

    });

</script>

<style scoped>
    .header-container {
        height: 900px;
        margin:0;
    }
    .header-image {
        width:100%;
        height:100px;
        background-position: cover;
        margin:0  1.25rem 0 6.25rem;
    }
    .image {
        height:800px;
        width:100%;
    }
    .menu-container {
        position: absolute;
        top:0;
        left:0;
        z-index:1;
        height:6.25rem;
    }
    .menu-container:after {

    content: "";
    position: absolute;
    display: inline-block;
    width: 100%;
    height: .0625rem;
    opacity: .3;
    z-index: 2;
    background:#fff;
    }

</style>