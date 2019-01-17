<template>
  <div id="app">
    <div class="bpp ignore">
      bpp
    </div>
    <div flexcontainer>
      <div w-188-246 aspectratio>
        <div aspectratio-content>
          <img src="./assets/2222.png" alt="">
        </div> 
      </div>
      <div w-187-246 aspectratio>
        <div aspectratio-content>
          <img src="./assets/1111.png" alt="">  
        </div> 
      </div>
      <div w-188-246 aspectratio>
        <div aspectratio-content>
          <img src="./assets/2222.png" alt="">
        </div> 
      </div>
      <div w-187-246 aspectratio>
        <div aspectratio-content>
          <img src="./assets/1111.png" alt="">  
        </div> 
      </div>
    </div>

    <div class="line"></div>
    <div class="line1"></div>
    <router-view/>
  </div>
</template>

<style>
/* 哪些地方使用vw来适配页面
容器适配，可以使用vw
文本的适配，可以使用vw
大于1px的边框、圆角、阴影都可以使用vw
内距和外距，可以使用vw */

* {
  margin: 0;
  padding: 0;
}
#app {
  width: 750px;
  height: 100vh;
  background-color: pink;
  font-size: 30px;
}
.bpp {
  width: 325px;
  height: 100px;
  background-color: blue;
  border: .5px solid #eee;
}
.bpp.ignore {
  font-size: 30px;
}

/* 长宽比 */
[flexcontainer] {
  display: flex;
  width: 750px;
}
[aspectratio] {
  position: relative;
}
[aspectratio]::before {
  content: '';
  display: block;
  width: 1px;
  margin-left: -1px;
  height: 0;
}

[aspectratio-content] {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
  [aspectratio-content] img {
    width: 100%;
    height: 100%;
    vertical-align: top;
  }

[w-188-246] {
  aspect-ratio: '188:246';
}
[w-187-246] {
  aspect-ratio: '187:246';
}
[w-188-246] { 
  width: 188px; 
}
[w-187-246] { 
  width: 187px; 
}

/* 1px边框 */
@svg square { 
  @rect { 
    fill: var(--color, black); 
    width: 100%; 
    height: 100%; 
  } 
} 
.line {
  width: 300px;
  height: 300px;
  background-color: #fff;
  border: 0.5px solid red;
}
.line1 {
  width: 300px;
  height: 300px;
  /* background-color: red; */
}
.line1 {
  background: #ccc svg(square param(--color #00b1ff));

}
</style>

