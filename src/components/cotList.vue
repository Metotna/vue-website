<template>
<div class="cot-rb">
	<ul>
    <li v-for="x in cot">
      <img src="" width="85px" height="85px">
      <div>
        <h6>{{x.name}}</h6>
        <h3>{{x.url}}</h3>
        <el-button>文字按钮</el-button>
      </div>
    </li>
  </ul>
</div>
  
</template>
<script>
export default {
  data() {
    return {
      cot: [{
          name: 'part1',
          url: 'http://weixin.com'
        },
        {
          name: 'part2',
          url: 'http://twitter.com',
          hot: true
        },
        {
          name: 'part3',
          url: 'http://maps.com'
        },
        {
          name: 'part4',
          url: 'http://phone.com'
        }
      ]
    }
  }
}

</script>
<style>

.cot-rb {
  margin: 20px 0;
}

.cot-rb ul li {
  float: left;
  width: 40%;
  padding: 10px;
  border: 1px solid #ddd;
  margin-right: 20px;
  margin-bottom: 30px;
}

.cot-rb ul li img {
  float: left;
}

.cot-rb ul li div {
  margin-left: 95px;
  height: 85px;
  position: relative;
}

.cot-rb ul li div button {
  position: absolute;
  bottom: 0;
  left: 0;
}
</style>
