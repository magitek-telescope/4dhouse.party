<template>
  <div id="wrapper">
    <nuxt/>
  </div>
</template>

<style>
html {
  font-family: "YuGothic", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  line-height: 1.0;
}

html, body, #wrapper{
  width: 100%;
  min-height: 100vh;
  margin: 0;
  padding: 0;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

#wrapper{
  background: linear-gradient(to right, #fff 0, #fff 50%, #F9F9FB 50%, #F9F9FB 100%);
}

.container{
  width: 960px;
  margin: 0 auto;
}
</style>
