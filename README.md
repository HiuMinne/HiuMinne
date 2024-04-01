<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I Love You</title>
    <link rel="shortcut icon" href="./icon.png" type="image/x-icon">
    <link rel="stylesheet" href="main.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">
</head>
<body>

    <div id="drag-container">
        <div id="spin-container">
          <img src="https://i.pinimg.com/236x/09/fb/fa/09fbfa9bea517a7fc22e17eccf3b0efc.jpg" alt="">
          <img src="https://i.pinimg.com/474x/83/8f/8c/838f8c8ec3cc03e08cad9539713a4c90.jpg" alt="">
          <img src="https://i.pinimg.com/236x/28/ee/36/28ee361674946e0a4cb26d4ea8ade34e.jpg" alt="">
          <img src="https://i.pinimg.com/736x/e4/e4/b0/e4e4b0e7559fedb21159574999e3ecdc.jpg" alt="">
          <img src="https://i.pinimg.com/236x/cc/e8/cf/cce8cf9347b72aff733e40fa6a9c7674.jpg" alt="">
          <img src="https://i.pinimg.com/236x/aa/ef/e4/aaefe4bf6eb4cc11efead3429cfdb5ef.jpg" alt="">
          <img src="https://i.pinimg.com/564x/bb/c7/ba/bbc7ba6280d961d3e110c79311b5d5a9.jpg" alt="">
          <img src="https://i.pinimg.com/236x/c9/65/f3/c965f3beeaac25198df8cb60f7d8da36.jpg" alt="">

            <p>My Love</p>


        </div>
        <div id="ground"></div>
      </div>

      <div id="music-container"></div>
      <div id="canva">
      <canvas id="canvas"></canvas>
    </div>
    <audio src="./music.mp3" autoplay loop></audio>
    <script src="main.js"></script>
</body>
</html>
 160 changes: 160 additions & 0 deletions160  
main.css
@@ -0,0 +1,160 @@
* {
    margin: 0;
    padding: 0;
  }

  html,
  body {
    height: 100%;
    /* for touch screen */
    touch-action: none; 
  }

  body {
    overflow: hidden;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    background: #111;
    -webkit-perspective: 1000px;
            perspective: 1000px;
    -webkit-transform-style: preserve-3d;
            transform-style: preserve-3d;
  }

  #drag-container, #spin-container {
    position: relative;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    margin: auto;
    -webkit-transform-style: preserve-3d;
            transform-style: preserve-3d;
    -webkit-transform: rotateX(-10deg);
            transform: rotateX(-10deg);
            z-index: 100;
  }

  #drag-container img, #drag-container video {
    -webkit-transform-style: preserve-3d;
            transform-style: preserve-3d;
    position: absolute;
    left: 0;
    top: 0;
    max-width: 120%;
    max-height: 120%; 
    line-height: 200px;
    font-size: 50px;
    text-align: center;
    -webkit-box-shadow: 0 0 8px #fff;
            box-shadow: 0 0 8px #fff;
    -webkit-box-reflect: below 10px linear-gradient(transparent, transparent, #0005);
  }

  #drag-container img:hover, #drag-container video:hover {
    -webkit-box-shadow: 0 0 15px #fffd;
            box-shadow: 0 0 15px #fffd;
    -webkit-box-reflect: below 10px linear-gradient(transparent, transparent, #0007);
  }

  #drag-container p {

    position: absolute;
    top: 100%;
    left: 50%;
    -webkit-transform: translate(-50%,-50%) rotateX(90deg);
            transform: translate(-50%,-50%) rotateX(90deg);
    color: rgb(0, 195, 255);
    animation: fadein ease 15s;
  }

  @keyframes fadein {
      from {
          opacity:0;

      }
      to {
          opacity: 1;

      }
  }

  #ground {
    width: 900px;
    height: 900px;
    position: absolute;
    top: 100%;
    left: 50%;
    -webkit-transform: translate(-50%,-50%) rotateX(90deg);
            transform: translate(-50%,-50%) rotateX(90deg);
    background: -webkit-radial-gradient(center center, farthest-side , #9993, transparent);
  }

  #music-container {
    position: absolute;
    top: 0;
    left: 0;
    display: none;
  }

  @-webkit-keyframes spin {
    from{
      -webkit-transform: rotateY(0deg);
              transform: rotateY(0deg);
    } to{
      -webkit-transform: rotateY(360deg);
              transform: rotateY(360deg);
    }
  }

  @keyframes spin {
    from{
      -webkit-transform: rotateY(0deg);
              transform: rotateY(0deg);
    } to{
      -webkit-transform: rotateY(360deg);
              transform: rotateY(360deg);
    }
  }
  @-webkit-keyframes spinRevert {
    from{
      -webkit-transform: rotateY(360deg);
              transform: rotateY(360deg);
    } to{
      -webkit-transform: rotateY(0deg);
              transform: rotateY(0deg);
    }
  }
  @keyframes spinRevert {
    from{
      -webkit-transform: rotateY(360deg);
              transform: rotateY(360deg);
    } to{
      -webkit-transform: rotateY(0deg);
              transform: rotateY(0deg);
    }
  }

  #canvas {
    background-color:transparent;   
    color: transparent; 
    margin: 0;
    overflow: hidden;
    background-repeat: no-repeat;
    width: 100vw;
  }


#canva {
    position: absolute;
    top: 0px;
    right: 0px;
    overflow: hidden;
}

p {
    font-family: 'Dancing Script', cursive;
    font-family: 'Rampart One', cursive;
    font-size: 4vw;

}
