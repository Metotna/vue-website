<template>
  <div class="listname">
    <div class="block">
      <!-- <span class="demonstration">默认 Hover 指示器触发</span> -->
      <el-carousel class="outbor" :interval="1500">
        <el-carousel-item v-for="(item,index) in imglist" :key="index" class="outbor">
          <div class="floattext"> <img :src='item.src' width="100%">
            <span>{{item.name}}</span></div>
        </el-carousel-item>
      </el-carousel>
    </div>
    <!--     <div class="block">
      <span class="demonstration">Click 指示器触发</span>
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="(item,index) in imglist" :key="index" >
          <img :src='item.src'  width="100%">
        </el-carousel-item>
      </el-carousel>
    </div> --> 
  </div>
</template>
<style>
.outbor {
  width: 780px;
  height: 438px !important;
}

.outbor .el-carousel__container {
  height: 438px !important;
}

.listname {
  width: 80%;
}

.floattext {
  position: relative;
}

.floattext img {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
}

.floattext span {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 5;
  padding: 30px;
  font-size: 30px;
  color: #fff;
}

.block {
  margin: 50px auto;
}

.block h3 {
  text-align: center;
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;

  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}

</style>
<script>
export default {
  data() {
    return {
      imglist: [{
          src: '../static/img/5.jpg',
          name: 'Marvel'
        },
        {
          src: '../static/img/1.jpg',
          name: 'Marvel-Ultron'
        },
        {
          src: '../static/img/2.jpg',
          name: 'Marvel-Deadpool'
        },
        {
          src: '../static/img/4.jpg',
          name: 'Marvel-Iron Man'
        },
        {
          src: '../static/img/3.jpg',
          name: 'Marvel-Captain America'
        },
        {
          src: '../static/img/6.jpg',
          name: 'Marvel-Civil War'
        },
      ]
    }
  }
}

</script>
<style>


</style>
