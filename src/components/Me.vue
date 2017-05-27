<template>
  <div class="me">
    <a class="resume" href="https://github.com/Chenchangsheng1990/resume" target="_blank">{{resume}}</a>
    <Load></Load>
  </div>
</template>

<script>
import Load from './Load'
export default {
  name: 'me',
  data () {
    return {
      resume: 'My Resume'
    }
  },
  created () {
    window.onload = function () {
      document.querySelector('.load').style.display = 'none'
    }
  },
  components: {
    Load
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus">
.me{
  height: 100%;
  width: 100%;
  display: flex;
  background-size: 100% 100%;
  justify-content: center;
  align-items: center;
  .resume{
    height: 40px;
    width: 100px;
    font-size: 25px;
    color: #40A5ED;
    text-align: center;
    line-height: 40px;
    display: inline-block;
    border-bottom: 1px solid #eee;
    transition: all 1s;
  }
  .resume:hover{
    color: green;
    border-color: green;
    transform: scale(1.5);
  }
}
</style>
