<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>StarPopper: Meme Final Boss</title>
  <style>
    body {
      margin: 0;
      background: radial-gradient(circle at 30% 70%, #1a0033 0%, #000011 50%, #000000 100%);
      font-family: 'Orbitron', sans-serif;
      height: 100vh;
      overflow: hidden;
      color: #fff;
      cursor: crosshair;
    }
    .stars { position: absolute; width:200%; height:200%; animation: spinStars 60s linear infinite; }
    @keyframes spinStars { 0%{transform:rotate(0);} 100%{transform:rotate(360deg);} }
    .star { position:absolute; background:white; border-radius:50%; opacity:0.5; }
    .robot { position:absolute; left:50%; top:50%; transform:translate(-50%,-50%); width:280px; height:380px;
      background:linear-gradient(45deg,#e6e6fa,#c0c0c0,#708090); border-radius:20px;
      box-shadow:0 0 50px rgba(0,255,255,0.4), inset 0 0 20px rgba(255,255,255,0.2);
      animation: floatBot 4s ease-in-out infinite;
    }
    @keyframes floatBot { 0%,100%{transform:translate(-50%,-50%) translateY(0);} 50%{transform:translate(-50%,-50%) translateY(-20px);} }
    .sticker {
      position:absolute; width:80px; height:80px; background-size:cover;
      border: 3px solid transparent; border-radius:12px; animation: pulseBorder 1.5s infinite;
    }
    @keyframes pulseBorder {
      0% { border-color: hsl(300, 100%, 60%); }
      50% { border-color: hsl(200, 100%, 60%); }
      100% { border-color: hsl(100, 100%, 60%); }
    }
    .health { position:fixed; top:10px; left:50%; transform:translateX(-50%); width:300px; height:20px; background:#333;
      border:2px solid #00ffff; border-radius:10px; overflow:hidden; z-index:100; }
    .health-bar { height:100%; background:#00ff00; width:100%; transition:width .2s; }
    .glitchKO {
      position:fixed; top:50%; left:50%; transform:translate(-50%,-50%);
      font-size:60px; font-weight:bold; color:#ff00ff;
      text-shadow:2px 0 #00ffff,-2px 0 #ffff00,0 2px #00ff00,0 -2px #ff0000;
      animation: glitchFlash 1s linear forwards;
    }
    @keyframes glitchFlash {
      0%{opacity:0;}10%,80%{opacity:1; transform:scale(1.2);}50%{transform:scale(.8) rotate(-2deg);}100%{opacity:0;}
    }
  </style>
</head>
<body>
  <div class="stars" id="stars"></div>
  <div class="health"><div class="health-bar" i
