<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dancing Silhouette</title>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    background: #ff2678;
    font-family: Arial, sans-serif;
  }

  .dance-stage {
    min-height: 500px;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    background: linear-gradient(
      135deg,
      #ff2678,
      #8c27ff,
      #ff7138
    );
    position: relative;
  }

  .dancer {
    width: min(80vw, 430px);
    overflow: visible;
    animation: groove 1.1s ease-in-out infinite alternate;
    transform-origin: 50% 85%;
  }

  .arm-left {
    transform-box: view-box;
    transform-origin: 145px 190px;
    animation: armLeft 0.55s ease-in-out infinite alternate;
  }

  .arm-right {
    transform-box: view-box;
    transform-origin: 230px 190px;
    animation: armRight 0.65s ease-in-out infinite alternate;
  }

  .leg-left {
    transform-box: view-box;
    transform-origin: 175px 300px;
    animation: legLeft 0.5s ease-in-out infinite alternate;
  }

  .leg-right {
    transform-box: view-box;
    transform-origin: 205px 300px;
    animation: legRight 0.6s ease-in-out infinite alternate;
  }

  .head {
    transform-box: view-box;
    transform-origin: 190px 110px;
    animation: headBob 0.55s ease-in-out infinite alternate;
  }

  @keyframes groove {
    from { transform: rotate(-5deg) translateY(5px); }
    to   { transform: rotate(5deg) translateY(-9px); }
  }

  @keyframes armLeft {
    from { transform: rotate(20deg); }
    to   { transform: rotate(-35deg); }
  }

  @keyframes armRight {
    from { transform: rotate(-25deg); }
    to   { transform: rotate(35deg); }
  }

  @keyframes legLeft {
    from { transform: rotate(-15deg); }
    to   { transform: rotate(20deg); }
  }

  @keyframes legRight {
    from { transform: rotate(20deg); }
    to   { transform: rotate(-15deg); }
  }

  @keyframes headBob {
    from { transform: rotate(-8deg); }
    to   { transform: rotate(8deg); }
  }

  @media (prefers-reduced-motion: reduce) {
    .dancer, .dancer * {
      animation: none !important;
    }
  }
</style>
</head>

<body>
<div class="dance-stage">

  <svg class="dancer" viewBox="0 0 380 420"
       xmlns="http://www.w3.org/2000/svg"
       role="img" aria-label="Animated dancing woman silhouette">

    <!-- Legs -->
    <g fill="none" stroke="#101010"
       stroke-width="29" stroke-linecap="round">
      <path class="leg-left"
        d="M175 288 Q150 327 130 370 L110 390"/>
      <path class="leg-right"
        d="M205 288 Q235 320 245 355 L270 365"/>
    </g>

    <!-- Shoes -->
    <g fill="#101010">
      <ellipse cx="103" cy="393" rx="23" ry="9"
               transform="rotate(-18 103 393)"/>
      <ellipse cx="276" cy="369" rx="24" ry="9"
               transform="rotate(15 276 369)"/>
    </g>

    <!-- Body -->
    <path fill="#101010"
      d="M160 160
         Q187 147 215 164
         L230 228
         Q225 263 214 300
         L164 300
         Q151 263 153 228 Z"/>

    <!-- Left arm -->
    <g class="arm-left" fill="none"
       stroke="#101010" stroke-width="25"
       stroke-linecap="round" stroke-linejoin="round">
      <path d="M158 178 Q120 165 102 130 L75 103"/>
    </g>

    <!-- Right arm -->
    <g class="arm-right" fill="none"
       stroke="#101010" stroke-width="25"
       stroke-linecap="round" stroke-linejoin="round">
      <path d="M218 178 Q251 163 265 130 L290 111"/>
    </g>

    <!-- Hands -->
    <g fill="#101010">
      <circle cx="75" cy="103" r="13"/>
      <circle cx="290" cy="111" r="13"/>
    </g>

    <!-- Neck -->
    <path fill="#101010"
      d="M178 137 L178 165 L203 165 L202 137 Z"/>

    <!-- Head -->
    <g class="head">
      <ellipse cx="190" cy="108" rx="35" ry="43"
               fill="#101010"/>

      <!-- Hair silhouette -->
      <path fill="#101010"
        d="M157 108 Q142 69 178 59
           Q218 48 224 89
           L216 101 Q203 76 183 82
           Q170 91 157 108 Z"/>

      <!-- White retro headphones -->
      <path d="M153 111
               Q146 58 190 57
               Q233 58 227 111"
            fill="none" stroke="#fff"
            stroke-width="8" stroke-linecap="round"/>

      <rect x="148" y="96" width="13" height="29"
            rx="5" fill="#fff"/>
      <rect x="219" y="96" width="13" height="29"
            rx="5" fill="#fff"/>
    </g>

  </svg>
</div>
</body>
</html>
