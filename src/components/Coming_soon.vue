<template>
        <!--电影列表开始-->
        <div class="list coming_soon">
            <ul>

                <li v-for="item in arr">
                    <a href="#/details">
                        <img :src="item.images.large" alt="">
                    </a>
                    <div class="meta">
                        <h4><span>{{item.title}}</span> <em>{{item.rating.average}}分</em></h4>
                        <div class="otherinfo">类型:<span v-for="item1 in item.genres">{{item1}}</span></div>
                    </div>
                </li>
                
            </ul>
            <div class="paging">
                <label>总共：0条记录,第0/0页;</label>
                <!-- 加上disable类样式，表示按钮禁用状态 -->
                <button class="prev disable ">上一页</button>
                <button class="next">下一页</button>
            </div>
        </div>
        <!--电影列表结束-->  
</template>

<script>
export default {
  name:'coming_soon',
  created:function(){
    this.getData();
  },
  data:function(){
      return {
          arr:[]
      }
  },
  methods:{
      getData:function(){
          var that = this;
         //   在这个created的阶段把数据从后台请求回来,把它给我们的数据模型
        this.$jsonp('http://api.douban.com/v2/movie/coming_soon',{start:0,count:10}).then(function(data){
            // console.log(data);
            that.arr = data.subjects;
        })
      }
  }
}
</script>

<style>

</style>
