<template>
  <header>
    <h1 class="title">TODOIST</h1>
    <span class="sub_tit">CREATIVE PORTFOLIO<br>CODING AND DESIGN</span>
    <span class="deco"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M0 7.33l2.829-2.83 9.175 9.339 9.167-9.339 2.829 2.83-11.996 12.17z"/></svg></span>
  </header>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style>
.title {
  letter-spacing: 10px;
  font-size: 30px;
  margin-bottom: 8px;
  text-align: center;
  font-weight: lighter;
}
.sub_tit{
  display: block;
  position: relative;
  text-align: center;
  padding-bottom: 80px;
  font-size: 11px;
  line-height: 1.3;
}
.deco {
  position: absolute;
  top: 110px;
  left: 50%;
  margin-left: -12px;
  animation: deco 1.5s infinite;
}
@keyframes deco {
  0% {top:105px}
  50% {top: 110px}
}
</style>