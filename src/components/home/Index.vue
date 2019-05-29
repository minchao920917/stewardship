<template>
    <div id="index">
      <div class="container">
        <Swiper ref="swiper" @transtionend="getNum" v-if="imgList.length>0">
          <Slide v-for="(item,index) in imgList" :key=index>
            <img :src="item.img" />
          </Slide>
        </Swiper>
        <div class="notice">
          <p class="title">
            <span class="icon icon-notice"></span>
            公告
          </p>
        </div>
          <ul class="notice-items">
            <li class="notice-item" v-for="(item,index) in noticList" :key=index>
              <a href=""><p>{{index + 1 }}. {{item.title}}</p></a>
            </li>
          </ul>

        <div class="news">
          <a href="#/home/news" class="title">
            <span class="icon icon-news"></span>
            精选资讯
            <span class="more" >···</span>
          </a>
          <ul class="news-items">
            <li class="news-item" v-for="(item,index) in newsList" :key=index>
              <a href="item.url">
                <p class="news-title">{{item.title}}</p>
                <p class="news-desc">{{item.desc}}</p>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
</template>
<script>
import { Swiper, Slide } from 'vue-swiper-component'
export default {
  name: 'Index',
  data () {
    return {
      imgList: [
        { img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360' },
        { img: 'https://qiniu.epipe.cn/5430983074181545984?imageslim&imageView2/1/w/750/h/360' },
        { img: 'https://qiniu.epipe.cn/5464226412548325376?imageslim&imageView2/1/w/750/h/360' }
      ],
      noticList: [
        {
          url: '',
          title: '了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意'
        },
        {
          url: '',
          title: '保持童心接近孩子的心灵'
        },
        {
          url: '',
          title: '必不可少的三大家庭教育'
        },
        {
          url: '',
          title: '必不可少的三大家庭教育'
        }
      ],
      newsList: [
        {
          url: '',
          img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360',
          title: '保持童心接近孩子的心灵',
          desc: '为了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意，原因何在呢？主要是由于父母教育孩子的方式不正确所致。其实为…'
        },
        {
          url: '',
          img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360',
          title: '做个“三心”父母',
          desc: '为了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意，原因何在呢？主要是由于父母教育孩子的方式不正确所致。其实为…'
        },
        {
          url: '',
          img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360',
          title: '父母就是孩子的“镜子”',
          desc: '为了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意，原因何在呢？主要是由于父母教育孩子的方式不正确所致。其实为…'
        },
        {
          url: '',
          img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360',
          title: '必不可少的三大家庭教育',
          desc: '为了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意，原因何在呢？主要是由于父母教育孩子的方式不正确所致。其实为…'
        },
        {
          url: '',
          img: 'https://qiniu.epipe.cn/5456575529551388672?imageslim&imageView2/1/w/750/h/360',
          title: '必不可少的三大家庭教育',
          desc: '为了子女的锦绣前程，每一个做父母的都用心良苦，而最后的结果常常不尽如人意，原因何在呢？主要是由于父母教育孩子的方式不正确所致。其实为…'
        }

      ]
    }
  },
  components: {
    Swiper,
    Slide
  },
  methods: {
    getNum (i) {
      // this.$toast(`==当前滑到了第${i}个`, 400)
      // console.log(i)
    }
  }
}
</script>

<style scoped>
  .icon-users{
    background: url(./../../../static/images/users.png);
  }
  .icon-sl{
    background: url(./../../../static/images/sl.png);
  }
  .icon-news{
    background: url(./../../../static/images/news_act.png);
  }
  .icon-notice{
    background: url(./../../../static/images/notice.png);
  }
  .container{
    background: #f3f3f3;
    /*height: 5.90rem;*/
    overflow-x: hidden;
    overflow-y: auto;
  }
  .news,.notice{
    background: #fff;
    margin-top: .2rem;
  }
  .title{
    display: block;
    margin-top: 0;
    max-width: 7.5rem;
    padding: .1rem .2rem .1rem .7rem;
    text-align: left;
    border-bottom: 1px solid #f3f3f3;
    position: relative;
  }
  .title .icon{
    position: absolute;
    left: .1rem;
    display: inline-block;
    width: .48rem;
    height: .48rem;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .more{
    float: right;
    color: #666;
    font-size: .28rem;
    line-height: .52rem;
    font-weight: bolder;
  }
  .notice{

  }
  .notice-items{
    display: block;
    width: 7.5rem;
    height: 5rem;
    background: url(../../assets/notic-bg.png) no-repeat center;
    background-size: cover;
  }
  .notice-item{
    display: block;
  }
  .notice-item a{
    display: block;
    position: relative;
    top: .6rem;
    font-size: .32rem;
    line-height: 1rem;
    font-weight: bolder;
  }
  .notice-item a p{
    width: 85%;
    margin: 0 auto;
    color: #f60;
    overflow: hidden;/*内容超出后隐藏*/
    text-overflow: ellipsis;/* 超出内容显示为省略号*/
    white-space: nowrap;/*文本不进行换行*/
    text-align: left;

  }
  .news{
    margin-bottom: 2rem;
  }
  .news-items{
    /*background: ;*/
  }
  .news-item{
    padding: .2rem .05rem;
    display: block;
    width: 95%;
    margin: .2rem auto;
    border-bottom: 1px dashed #999;
  }
  .news-item .news-title{
    width: 90%;
    /*margin:0 auto;*/
    padding: .1rem 0;
    overflow: hidden;/*内容超出后隐藏*/
    text-overflow: ellipsis;/* 超出内容显示为省略号*/
    white-space: nowrap;/*文本不进行换行*/
    font-size: .32rem;
    text-align: left;
    font-weight: bold;
    text-indent: .2rem;
  }
  .news-item .news-desc{
    font-size: .24rem;
    text-align: left;
    text-indent: .2rem;
    line-height: .4rem;
    overflow: hidden;/*内容超出后隐藏*/
    text-overflow: ellipsis;/* 超出内容显示为省略号*/
    /*white-space: nowrap;!*文本不进行换行*!*/
  }
</style>
