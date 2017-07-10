<template>
  <div>
    <pre><div id="app" class="styleEditor" ref="goto">{{code}}</div></pre>
    <div class="resumeEditor">
      <div class='owl'>
        <div class='body'>
          <div class='wing'></div>
          <div class='wing'></div>
          <div class='feet'></div>
          <div class='feet right'></div>
          <div class='feather'></div>
        </div>
        <div class='head'>
          <div class='eyes'>
            <div class='beak'></div>
            <div class='eye'>
              <div class='pupil'></div>
            </div>
            <div class='eye'>
              <div class='pupil'></div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div v-html="styleCode"></div>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {

  },
  data() {
    return {
      code: '',
      finalCode: `
/*Inspired by http://strml.net/
*/
* {
  -webkit-transition: all .3s;
  -o-transition: all .3s;
  transition: all .3s;
}
html {
  color: rgb(222,222,222); 
  background: rgb(39,40,34); 
}
.styleEditor {
  padding: .5em;
  border: 1px solid;
  margin: .5em;
  overflow: auto;
  width: 45vw; height: 90vh;
}
html{
  -webkit-perspective: 1000px;
          perspective: 1000px;
}
.styleEditor {
  position: fixed; left: 0; top: 0; 
  -webkit-transition: none; 
  -o-transition: none; 
  transition: none;
  -webkit-transform: rotateY(10deg) translateZ(-100px) ;
          transform: rotateY(10deg) translateZ(-100px) ;
}
.resumeEditor{
  position: fixed; right: 0; top: 0;
  padding: .5em;  margin: .5em;
  width: 48vw; height: 90vh; 
  border: 1px solid;
  background: white; color: #222;
  overflow: auto;
}
.resumeEditor{
  padding: 2em;
}
.resumeEditor h2{
  display: inline-block;
  border-bottom: 1px solid;
  margin: 1em 0 .5em;
}
.resumeEditor ul,.resumeEditor ol{
  list-style: none;
}
.resumeEditor ul> li::before{
  content: '•';
  margin-right: .5em;
}
.resumeEditor ol {
  counter-reset: section;
}
.resumeEditor ol li::before {
  counter-increment: section;            
  content: counters(section, ".") " ";  
  margin-right: .5em;
}
.resumeEditor blockquote {
  margin: 1em;
  padding: .5em;
  background: #ddd;
}
.owl {
  position: relative;
  margin: 20% auto;
  width: 200px;
}
.pupil {
  position: absolute;
  top: 20px;
  left: 20px;
  width: 50px;
  height: 50px;
  border-radius: 25px;
  background: #000;
}
.pupil::after {
  position: absolute;
  top: 0;
  right: 0;
  display: block;
  width: 24px;
  height: 24px;
  border-radius: 12px;
  background: #fff;
  content: '';
}
.eye {
  position: absolute;
  top: 10px;
  left: 10px;
  width: 90px;
  height: 90px;
  border-radius: 45px;
  background: #fff;
}
.eye:nth-child(2){
  left:98px;
}
.eyes {
  position: absolute;
  top: 10px;
  left: -20px;
  width: 110px;
  height: 110px;
  border-radius: 50%;
  background: #98e0f8;
}
.eyes::before {
  position: absolute;
  left: 88px;
  display: block;
  width: 110px;
  height: 110px;
  border-radius: 50%;
  background: #98e0f8;
  content: '';
}
.beak {
  position: absolute;
    border-top: 60px solid #ef8e1b; 
  border-right: 50px solid transparent;
  border-left: 50px solid transparent;
  content: '';
    top: 60px;
  left: 49px;
}
.head {
  position: absolute;
  width: 160px;
  height: 80px;
  border-radius: 80px / 40px;
  background: #64c2de;
  top: 10px;
}
.head::before {
  position: absolute;
  top: 0px;
  left: 15px;
  display: block;
  border-right: 15px solid transparent;
  border-bottom: 15px solid #64c2de; 
  border-left: 15px solid transparent;
  content: ''; 
  -webkit-transform: rotate(-15deg); 
      -ms-transform: rotate(-15deg); 
          transform: rotate(-15deg);
}
.head::after {
  position: absolute;
  top: 0;
  right: 18px;
  z-index:-1;
  display: block;
  width: 0;
  height: 0; 
  border-right: 15px solid transparent;
  border-bottom: 15px solid #64c2de; 
  border-left: 15px solid transparent;
  content: ''; 
  -webkit-transform: rotate(15deg); 
      -ms-transform: rotate(15deg); 
          transform: rotate(15deg);
}
.body{
  position: absolute;
  top: 100px;
  width: 160px;
  height: 100px;
  border-radius: 80px / 50px;
  background: #98e0f8;
}
.wing {
  position: absolute;
  height: 100px;
  border-radius: 50px 0;
  background: #64c2de;
   left: -20px;
  width: 50px;
  -webkit-transform-origin: 30px 10px;
      -ms-transform-origin: 30px 10px;
          transform-origin: 30px 10px;
  -webkit-transform: rotate(-20deg);
      -ms-transform: rotate(-20deg);
          transform: rotate(-20deg);
  -webkit-transition: all 0.5s ease;
  -o-transition: all 0.5s ease;
  transition: all 0.5s ease;
 }
.wing:nth-child(2) {
  left:130px;
  border-radius: 0 50px;
  -webkit-transform-origin: 20px 10px;
      -ms-transform-origin: 20px 10px;
          transform-origin: 20px 10px;
  -webkit-transform: rotate(20deg);
      -ms-transform: rotate(20deg);
          transform: rotate(20deg);
}
.feet {
  position: absolute;
  bottom: -5px;
  left: 50px;
  width: 6px;
  height: 18px;
  border-radius: 3px / 9px;
  background: #ef8e1b;
  -webkit-transform: rotate(10deg);
      -ms-transform: rotate(10deg);
          transform: rotate(10deg);
}
.feet::before {
  position: absolute;
  bottom: 0;
  left: -6px;
  display: block;
  width: 6px;
  height: 18px;
  border-radius: 3px / 9px;
  background: #ef8e1b;
  content: '';
}
.feet::after {
  position: absolute;
  bottom: 0;
  left: 6px;
  display: block;
  width: 6px;
  height: 18px;
  border-radius: 3px / 9px;
  background: #ef8e1b;
  content: '';
}
.feet.right {
  left: 104px;
  -webkit-transform: rotate(-10deg);
      -ms-transform: rotate(-10deg);
          transform: rotate(-10deg);
}
.owl:hover .wing {
  -webkit-transform: rotate(90deg);
      -ms-transform: rotate(90deg);
          transform: rotate(90deg);
}
.owl:hover .wing:nth-child(2) {
  -webkit-transform: rotate(-90deg);
      -ms-transform: rotate(-90deg);
          transform: rotate(-90deg);
}
      `
    }
  },
  created() {
    var n = 0
    let timer = setInterval(() => {
      var elem = document.getElementById('app')
      var codeLength = this.finalCode.length
      var elemLength = elem.firstChild.length
      if (codeLength === elemLength) {
        clearInterval(timer)
      }
      this.code = this.finalCode.substring(0, n)
      n += 1
      elem.scrollTop = elem.scrollHeight;
    }, 0)
  },
  computed: {
    styleCode() {
      return '<style>' + this.code + '</style>'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
