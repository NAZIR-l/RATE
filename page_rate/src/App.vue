<template>
  <nav>
    <h3> Mortgage Calculator </h3>
<img src="./assets/logo.1738c2dc.png" alt="">
  </nav>
  <router-view/>
</template>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  display: block;
  align-items: center;
  justify-content:flex-start;
  flex-direction:column;
  width:  100%;
  height:75vh;
  border-radius: 10px;
  padding: 20px;
  /* overflow: auto; */
}
*{
  padding:0;
  margin:0;
}
body{
  background-color:#333;
  display: flex;
  align-items: center;
  justify-content:center;
  height:100vh;
}
#app img{
    position:absolute;
  top:0;
  left:0;
  width:190px;
  height: 60px;
}
#app h3{
  font-size:3em;
  font-weight:800;
  padding-bottom: 20px;
}
</style>
