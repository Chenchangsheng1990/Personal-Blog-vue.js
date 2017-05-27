<template>
  <div class="welcome">
    <div class="dialog">
      <img src="../assets/welcome/imccs.jpg"/>
      <h1>{{title}}</h1>
      <p>{{msg1}}</p>
      <p>{{msg2}}</p>
      <p>{{msg3}}</p>
    </div>
    <Load></Load>
  </div>
</template>

<script>
import Load from './Load'
export default {
  name: 'welcome',
  data () {
    return {
      title: 'I am a Lion',
      msg1: '当你看见我流下眼泪的时候，',
      msg2: '那么说明你是真的把我的真心夺走了，',
      msg3: '因为作为一只萌萌哒的狮子真的很需要一份值得的依靠！',
      welImg: require('../assets/welcome/welcome.jpg')
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

<style lang="stylus">
.welcome{
  height: 100%;
  width: 100%;
  background: url(../assets/welcome/welcome.jpg) no-repeat;
  background-size: 100% 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  .dialog{
    width: 550px;
    overflow: hidden;
    background: #fff;
    border-radius: 5px;
    text-align: center;
    padding-bottom: 30px;
    animation: shake 0.5s 2 linear;
    @keyframes shake{
      0%{transform: translateX(0px);}
      25%{transform: translateX(40px);}
      50%{transform: translateX(0px);}
      75%{transform: translateX(-40px);}
      100%{transform: translateX(0px);}
    }
    img{
      width: 100%;
    }
    h1{
      font-size: 30px;
      margin: 20px 0;
      font-weight: bold;
    }
    p{
      padding: 8px 12px;
      font-size: 18px;
    }
  }
}
@media only screen and (max-width: 800px) {
	.welcome .dialog{
	  width: 80%;
	  p{
	    font-size: 12px;
	  }
	}
}
</style>
