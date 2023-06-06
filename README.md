HTML CODE

<!DOCTYPE html>
<html>
<head>
 <meta charset="utf-8">
 <meta name="viewport" content="width=device-width, initial-scale=1">
 <title>light</title>
 <link rel="stylesheet" type="text/css" href="light.css">
</head>
<body>
 <div class="cube">
  <div class="top"> </div>
   <div>
    <span style="--i:0;"></span>
    <span style="--i:1;"></span>
    <span style="--i:2;"></span>
    <span style="--i:3;"></span>
   </div>
 </div>
</body>
</html>

-----------------------------------------------------------------------------------------------

CSS CODE

*
{
 margin: 0;
 padding: 0;
 box-sizing: border-box;
}
body
{
 display: flex;
 justify-content: center;
 align-items: center;
 min-height: 100vh;
 background: #050505;
}
.cube
{
 position: relative;
 width: 300px;
 height: 300px;
 transform-style: preserve-3d;
 transform: rotateX(-30deg);
 animation: animate 4s linear infinite;
}
@keyframes animate
{
 0%
 {
  transform: rotateX(-30deg) rotateY(0deg);
 }
 100%
 {
  transform: rotateX(-30deg) rotateY(360deg);
 }
}
.cube div
{
 position: absolute;
 top: 0;
 left: 0;
 width: 100%;
 height: 100%;
 transform-style: preserve-3d;
}
.cube div span
{
 position: absolute;
 top: 0;
 left: 0;
 width: 100%;
 height: 100%;
 background: #f00;
 background: linear-gradient(#151515, #00ec00);
 transform: rotateY(calc(90deg * var(--i))) translateZ(150px);
}
.top
{
 position: absolute;
 top: 0;
 left: 0;
 width: 300px;
 height: 300px;
 background: #222;
 transform: rotateX(90deg) translateZ(150px);
}
.top::before
{
 content: '';
 position: absolute;
 top: 0;
 left: 0;
 width: 300px;
 height: 300px;
 background: #0f0;
 transform: translateZ(-380px);
 filter: blur(20px);
 box-shadow: 0 0 120px rgba(0, 255, 0, 0.2),
 0 0 200px rgba(0, 255, 0, 0.4),
 rgba(0, 255, 0, 0.6),
 rgba(0, 255, 0, 0.8),
 rgba(0, 255, 0, 1),;

}
