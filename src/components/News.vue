<template>
  <div class="news">
    <h2>新浪新闻</h2>
    <div class="main"></div>
    <button class="more" @click='loadMore' v-show='false'>加载更多</button>
    <Load></Load>
  </div>
</template>

<script>
import $ from 'jquery'
import Load from './Load'
export default {
  name: 'news',
  data () {
    return {
      item: [{
        title: '推荐'
      }, {
        title: '要闻'
      }, {
        title: '财经'
      }, {
        title: '科技'
      }],
      news: [],
      url: 'https://route.showapi.com/109-35?&needContent=0&needHtml=1&showapi_appid=34477&showapi_sign=cfa5957a730f43d38886bd16469b2a86&channelId=5572a108b3cdc86cf39001cd&page='
    }
  },
  created () {
    let [page, self] = [0, this]
    askData(this.url)
    function askData (url) {
      page++
      $.ajax({
        type: 'get',
        url: url + page,
        async: true,
        success: function (res) {
          self.news = res.showapi_res_body.pagebean.contentlist
          if (self.news.length === 0) {
            return false
          }
          $('.load').hide()
          loadNews(self.news)
        },
        error: function (err) {
          console.log(err)
        }
      })
    }
    function loadNews (data) {
      for (let i in data) {
        let html = `<div class="item">
        <a href="${data[i].link}">
          <p>
            <span class="see">${data[i].source}</span>
            <span class="time">${data[i].pubDate}</span>
          </p>
          <h3>${data[i].title}</h3>
          <p class="info">${data[i].desc}</p>
        </a>
        </div>`
        $(html).appendTo('.news .main')
      }
    }
  },
  methods: {
    loadMore () {
      let [page, self] = [1, this]
      askData(this.url)
      function askData (url) {
        page++
        $.ajax({
          type: 'get',
          url: url + page,
          async: true,
          success: function (res) {
            self.news = res.showapi_res_body.pagebean.contentlist
            if (self.news.length === 0) {
              return false
            }
            loadNews(self.news)
          },
          error: function (err) {
            console.log(err)
          }
        })
      }
      function loadNews (data) {
        for (let i in data) {
          let html = `<div class="item">
            <p><span class="see">${data[i].source}</span><span class="time">${data[i].pubDate}</span></p>
            <h3>${data[i].title}</h3>
            <p class="info">${data[i].html}</p>
          </div>`
          $(html).appendTo('.main')
        }
      }
    }
  },
  components: {
    Load
  }
}
</script>

<style lang="stylus">
.news{
  h2{
    width:100%;
    height:60px;
    text-align:center;
    font-size:30px;
    font-weight:bold;
    line-height:60px;
    color:#0096b6;
  }
  .main{
     .item{
      margin: 10px;
      margin-bottom:25px;
      border-bottom: 1px solid #0096b6;
      img{
        height: 150px;
      }
      .see{
        font-size: 16px;
        color: red;
        margin-right: 10px;
      }
      .time{
        font-size:12px;
      }
      h3{
        color: #000;
        font-size: 20px;
        font-weight: bold;
        margin: 10px;
      }
      p.info{
        line-height: 1.4;
        margin: 10px;
        color: #333;
        font-size:14px;
      }
    }
  }
}
</style>
