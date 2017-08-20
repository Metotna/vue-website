<template>
  <div class="cot-wrap">
    <div class="cot-left">
      <div class="lists" v-for="x in productList">
        <ul>
          <li>{{x.title}}</li>
          <li v-for=" y in x.list">{{y.name}}</li>
        </ul>
      </div>
    </div>
    <div class="cot-right">
      <div>{{msg}}</div>
      <el-button @click="clickmod(0)">按钮A</el-button>
      <el-button @click="clickmod(1)">按钮B</el-button>
      <el-button @click="check()">按钮C</el-button>
      <input type="file" name="" ref="files">
      <img :src="srcs">
      <transition>
        <components :is="modules"></components>
      </transition>
    </div>
  </div>
</template>
<script>
import cota from '../components/cota'
import cotList from '../components/cotList'
export default {
  name: 'index',
  data() {
    return {
      modules: '',
      srcs: '',
      msg: 'i am a person.',
      productList: {
        pc: {
          title: 'PC产品',
          list: [{
              name: '数据统计',
              url: 'http://starcraft.com'
            },
            {
              name: '数据预测',
              url: 'http://warcraft.com'
            },
            {
              name: '流量分析',
              url: 'http://overwatch.com',
              hot: true
            },
            {
              name: '广告发布',
              url: 'http://hearstone.com'
            }
          ]
        },
        app: {
          title: '手机应用类',
          last: true,
          list: [{
              name: '91助手',
              url: 'http://weixin.com'
            },
            {
              name: '产品助手',
              url: 'http://twitter.com',
              hot: true
            },
            {
              name: '智能地图',
              url: 'http://maps.com'
            },
            {
              name: '团队语音',
              url: 'http://phone.com'
            }
          ]
        },

      },
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
  },
  components: {
    cota,
    cotList
  },
  methods: {
    clickmod(a) {
      console.log(a)
      if (a == 0) {
        this.modules = cotList;
      } else {
        this.modules = cota;
      }
    },
    check() {
      var file = this.$refs.files.files[0]; //获取file对象 
      console.log(this.$refs.files.value)
      this.srcs = this.$refs.files.value;
      //判断file的类型是不是图片类型。 
      if (!/image\/\w+/.test(file.type)) {
        alert("请上传一张图片~");
        return false;
      }

      var reader = new FileReader(); //声明一个FileReader实例 
      reader.readAsDataURL(file); //调用readAsDataURL方法来读取选中的图像文件 
      reader.onload = function(e) {
        // 创建一个新增的图片和文字input 
        var figure = '<div class="figure"><div class="figure-hd">我的头部</div><div class="figure-bd"><img src="' + this.result + '" /><textarea placeholder="请输入文字"></textarea></div></div>';
        // figure.appendTo(this.$refs.efes); 
        window.localStorage.setItem("temp2", this.result)
        // this.srcs = this.result;
      }
      this.srcs = localStorage.getItem('temp2');
    }
  },
  watch: {

  }
}

</script>
<style>
.cot-wrap {
  overflow: hidden;
  background-color: #f0f0f0;
  min-width: 900px;
}

.cot-left {
  width: 150px;
  float: left;
}

.lists {
  margin-bottom: 20px;
  background-color: #fff;
}

.lists ul li {
  height: 30px;
  text-align: center;
  line-height: 30px;
  border-right: 1px solid #ddd;
  border-left: 1px solid #ddd;
  border-bottom: 1px solid #ddd;
}

.lists ul li:nth-child(1) {
  background-color: #41b883;
  border-top: 1px solid #ddd;
  color: #fff;
}

.cot-right {
  /*float: right;*/
  margin-left: 170px;
}

.cot-ra {
  overflow: hidden;
}

</style>
