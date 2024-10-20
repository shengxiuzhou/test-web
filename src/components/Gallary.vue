<template>
    <div class="gallary-container">
       <el-row>
            <el-col>推荐展馆</el-col>
       </el-row>
       <el-row :space-between="20">
            <el-col :span="12">
                <div class="mask-container">
                    <el-image :src="largeImgUrl.href" class="image"></el-image>
                    <div class="mask"></div>
                </div>
            </el-col>
            <el-col :span="12">
                <el-row type="flex" justify="space-around" :space-between="20">
                    <el-col :span="11" v-for="(img,index) in smallImgUrl" >
                        <el-image  class="image" :src="img"></el-image>
                    </el-col>
                </el-row>
            </el-col>
       </el-row>
   </div>
</template>


<script setup>
import {ref} from "vue"
const largeImgUrl = new URL('@/assets/images/test1.jpg', import.meta.url);
  console.log(largeImgUrl.href);
const smallImgUrl = [
    'https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20240325/6d139e31d3464210bfb5c171e2458198.png',
    'https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20230424/60ad11746e974e00a4ac39ccca12f4ad.png',
    'https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20230424/c2d63e5805a1444295ed745dc935e643.png',
    'https://cultureexpo-prod-1302844417.cos.ap-guangzhou.myqcloud.com//module/img/20230424/ee78461226c1465093260dd279fe0576.png'
  ];
</script>

<style scoped>
    .gallary-container {
        height:500px;
    }
    .image {
        width:100%;
        border-radius:10px;
    }
    .mask-container {
        position: relative;
        width:450px;
        height:450px;
    }
    .mask {
        position: absolute;
        top:0;
        left:0;
        width:100%;
        height:100%;
        border-radius:10px;
        background-color:rgba(0,0,0,0.5);
        opacity:0;
        transition: opacity 0.3s ease;

    }
    .mask-container:hover .mask {
        opacity: 1;
    }
</style>