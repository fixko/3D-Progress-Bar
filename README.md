# 3D Progress Bar

Animated 3D CSS Progress Bar

<div style="text-align:center; margin:10px">Watch the <a href="https://youtube.com/shorts/UAV16UmIukE" target="_blank">Animated 3D CSS Progress Bar</a> Youtube Video</div>
<div><br/></div>

```
<div class="wrap">
  <div class="cube">
    <div class="front">
      <div class="side">Loading ...</div>
    </div>
    <div class="back">
      <div class="side">Loading ...</div>
    </div>
    <div class="top">
      <div class="side">Loading ...</div>
    </div>
    <div class="bottom">
      <div class="side">Loading ...</div>
    </div>
  </div>
</div>

<style>
  .wrap {
    margin-top: 250px;
    perspective: 1000px;
    perspective-origin: 50% 50%;
    transform: rotateZ(0.01turn)
    rotateY(0.01turn);
  }
  .side {
    height: 100%;
    width: 30%;
    overflow: visible;
    font: 20px Verdana;
    color: #000;
    white-space: nowrap;
    text-align: center;
    line-height: 48px;
    border-right: solid 2px #666;
    background-size: 50px 50px;
    background-image: linear-gradient(135deg,
    #39f 25%,#9cf 25%,#9cf 50%,#39f 50%,
    #39f 75%, #9cf 75%, #9cf 100%);
    transition: width 2s ease;
    animation: bganim 1s linear 2s infinite;
  }
  .cube {
    margin: auto;
    position: relative;
    height: 50px;
    width: 500px;
    transform-style: preserve-3d;
    animation: rotate 20s infinite linear;
  }
  @keyframes rotate {
    100% { transform: rotateX(1turn); }
  }
  .cube > div {
    position: absolute;
    box-sizing: border-box;
    height: 100%;
    width: 100%;
    border: solid 1px #eee;
    background-size: 50px 50px;
    background-image: linear-gradient(135deg,
    #ddd 25%,#eee 25%,#eee 50%,#ddd 50%,
    #ddd 75%,#eee 75%,#eee 100%);
    animation: bganim 1s linear 2s infinite;
  }
  @keyframes bganim {
    to { background-position: 50px; }
  }
  .front {
    transform: translateZ(25px);
  }
  .back {
    transform: translateZ(-25px)
    rotateX(180deg);
  }
  .top {
    transform: rotateX(-270deg)
    translateY(-25px);
    transform-origin: top center;
  }
  .bottom {
    transform: rotateX(270deg)
    translateY(25px);
    transform-origin: bottom center;
  }
</style>

<script>
  var e = document.querySelectorAll('.side');
  let c = 0;
  var a = [0, 36, 88, 16, 72, 99, 43, 97]
  setInterval(function() {
    for (var i=0; i<e.length; i++) {
      e[i].style.width = a[c] + '%';
      e[i].innerHTML = 'Loading '+a[c]+'% ...';
    }
    c++;
    if (c==8) { c=0; }
  }, 3000);
</script>
```
