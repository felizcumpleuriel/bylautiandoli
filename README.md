<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Feliz cumpleeeeeee Uriel</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Luckiest+Guy&display=swap');

    body {
      margin: 0;
      padding: 0;
      font-family: 'Luckiest Guy', cursive;
      color: #fff;
      text-align: center;
      overflow-x: hidden;
      min-height: 100vh;
    }

    #bg-video {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      z-index: -1;
      pointer-events: none;
      filter: brightness(0.7) contrast(1.1) saturate(1.2);
      background: #000;
    }

    h1 {
      font-size: 4rem;
      margin-top: 50px;
      color: yellow;
      text-shadow: 3px 3px 0 red, 6px 6px 0 black;
      animation: shake 0.5s infinite alternate;
      z-index: 1;
      position: relative;
    }

    @keyframes shake {
      from { transform: rotate(-3deg); }
      to { transform: rotate(3deg); }
    }

    .gallery {
      display: none;
    }

    .carousel {
      width: 100vw;
      max-width: 500px;
      aspect-ratio: 1/1;
      margin: 40px auto 0 auto;
      position: relative;
      overflow: hidden;
      border-radius: 16px;
      box-shadow: 0 0 20px 4px #ff0a, 0 0 10px 2px #f00a;
      background: #222b;
      z-index: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 220px;
    }
    .carousel-img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: contain;
      opacity: 0;
      transition: opacity 0.7s;
      border: 5px solid yellow;
      box-shadow: 0 0 15px red;
      border-radius: 16px;
      background: #222;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .carousel-img.active {
      opacity: 1;
      z-index: 2;
    }

    audio {
      display: none;
    }

    /* Mobile styles */
    @media (max-width: 600px) {
      h1 {
        font-size: 2.2rem;
        margin-top: 25px;
        padding: 0 10px;
      }
      .carousel {
        width: 99vw;
        max-width: 99vw;
        aspect-ratio: 1/1;
        min-height: 160px;
        border-radius: 8px;
      }
      .carousel-img {
        border-width: 3px;
        box-shadow: 0 0 6px red;
        border-radius: 8px;
      }
      #bg-video {
        height: 100dvh;
        width: 100vw;
      }
    }
  </style>
</head>
<body>

  <video id="bg-video" autoplay loop muted playsinline poster="" preload="auto">
    <source src="fuego.mp4" type="video/mp4">
    Tu navegador no soporta el video de fondo.
  </video>

  <h1>Feliz cumpleeeeeee Uriel 🎉🔥</h1>

  <div class="carousel">
    <img class="carousel-img" src="1.jpeg" alt="Foto 1">
    <img class="carousel-img" src="2.jpeg" alt="Foto 2">
    <img class="carousel-img" src="3.jpeg" alt="Foto 3">
    <img class="carousel-img" src="4.jpeg" alt="Foto 4">
    <img class="carousel-img" src="5.jpeg" alt="Foto 5">
    <img class="carousel-img" src="6.jpeg" alt="Foto 6">
    <img class="carousel-img" src="7.jpeg" alt="Foto 7">
    <img class="carousel-img" src="8.jpeg" alt="Foto 8">
    <img class="carousel-img" src="9.jpeg" alt="Foto 9">
    <img class="carousel-img" src="10.jpeg" alt="Foto 10">
    <div class="carousel-img" id="carousel-img-11" style="background-image:url('11.jpeg'); background-size:contain; background-position:center; background-repeat:no-repeat;">
      <div class="carousel-text">Feliz cumpleeeeeeeee<br>con amor de parte de <b>lautiveelese</b></div>
    </div>
<style>
  .carousel-text {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    background: rgba(0,0,0,0.6);
    color: #fff700;
    font-size: 2rem;
    font-family: 'Luckiest Guy', cursive;
    padding: 18px 24px;
    border-radius: 16px;
    text-shadow: 2px 2px 8px #f00, 0 0 8px #000;
    text-align: center;
    max-width: 90%;
    z-index: 10;
    letter-spacing: 1px;
    pointer-events: none;
  }
  @media (max-width: 600px) {
    .carousel-text {
      font-size: 1.1rem;
      padding: 8px 6px;
      border-radius: 8px;
    }
  }
</style>
  </div>

  <audio id="bg-music" loop autoplay>
    <source src="TU-CANCION.mp3" type="audio/mpeg">
  </audio>
  <audio id="carousel-audio">
    <source src="tema.mp3" type="audio/mpeg">
  </audio>

  <script>
    
    const images = document.querySelectorAll('.carousel-img');
    const carouselAudio = document.getElementById('carousel-audio');
    let current = 0;
    function showImage(idx) {
      images.forEach((img, i) => img.classList.toggle('active', i === idx));
    }
    function nextImage() {
      current = (current + 1) % images.length;
      showImage(current);
    }
    showImage(current);
    setInterval(nextImage, 4000);

    
    let audioStarted = false;
    document.body.addEventListener('click', () => {
      document.getElementById('bg-music').play();
      if (carouselAudio && !audioStarted) {
        try {
          carouselAudio.pause();
          carouselAudio.currentTime = 0;
        } catch(e) {}
        carouselAudio.play();
        audioStarted = true;
      }
    }, { once: true });

    
    window.addEventListener('DOMContentLoaded', () => {
      const bgVideo = document.getElementById('bg-video');
      if (bgVideo) {
        bgVideo.pause();
      }
    });
  </script>
</body>
</html>
