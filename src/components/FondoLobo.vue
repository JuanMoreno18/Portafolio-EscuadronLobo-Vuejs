<template>
  <div class="stage">
    <canvas id="bgCanvas"></canvas>
    <canvas id="fgCanvas"></canvas>
    <img id="wolfImg" :src="wolfSrc" alt="wolf" crossorigin="anonymous" style="display:none" />
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import wolfSrc from '@/assets/lobo.png'

onMounted(() => {
  const bgCanvas = document.getElementById('bgCanvas')
  const fgCanvas = document.getElementById('fgCanvas')
  const bgCtx = bgCanvas.getContext('2d')
  const fgCtx = fgCanvas.getContext('2d')

  const W = window.innerWidth
  const H = window.innerHeight
  bgCanvas.width = fgCanvas.width = W
  bgCanvas.height = fgCanvas.height = H

  let particles = []
  let reveal = 0
function animate() {
  bgCtx.clearRect(0, 0, W, H)
  fgCtx.clearRect(0, 0, W, H)

  particles.forEach(p => {
    p.update()
    p.draw(fgCtx)
  })

  // controlar opacidad inicial
  if (reveal < 1) {
    fgCtx.globalAlpha = reveal
    reveal += 0.01
  } else {
    fgCtx.globalAlpha = 1
  }

  requestAnimationFrame(animate)
}
  let targets = []
  let letters = 'L O B O'.split('')
  const totalParticles = 2000

  class Particle {
    constructor(x, y, letter) {
      this.x = Math.random() * W
      this.y = Math.random() * H
      this.tx = x
      this.ty = y
      this.letter = letter
      this.size = 14
      this.speed = 0.05 + Math.random() * 0.05
    }
    update() {
      this.x += (this.tx - this.x) * this.speed
      this.y += (this.ty - this.y) * this.speed
    }
    draw(ctx) {
      ctx.font = `${this.size}px Arial Black`
      ctx.fillStyle = 'rgba(0, 255, 0, 0.9)' // Verde puro (RGB 0, 255, 0) y Alpha reducido a 0.4 (más transparente)
      ctx.shadowColor = '#0ff'
      ctx.shadowBlur = 10
      ctx.fillText(this.letter, this.x, this.y)
    }
  }

function buildTargetsFromImage(img) {
    const oc = document.createElement('canvas')
    const octx = oc.getContext('2d')

    const targetWidth = Math.min(W * 0.6, 500)
    const scale = targetWidth / img.width
    const targetHeight = Math.floor(img.height * scale)
    oc.width = targetWidth
    oc.height = targetHeight

    // Dibujar el lobo
    octx.drawImage(img, 0, 0, oc.width, oc.height)
    const imageData = octx.getImageData(0, 0, oc.width, oc.height).data

    const gap = 2 // densidad
    targets = []
    const offsetY = H * 0.55

    for (let y = 0; y < oc.height; y += gap) {
      for (let x = 0; x < oc.width; x += gap) {
        const i = (y * oc.width + x) * 4
        const r = imageData[i]
        const g = imageData[i + 1]
        const b = imageData[i + 2]
        const alpha = imageData[i + 3]

        // Detecta zonas oscuras o claras (mejor compatibilidad)
        const brightness = (r + g + b) / 3
        if (alpha > 80 && brightness < 230) {
          const cx = (W / 2 - oc.width / 3) + x   //Aca se puede cambiar la posicion del lobo
          const cy = offsetY - oc.height / 2 + y
          targets.push({ x: cx, y: cy })
        }
      }
    }
    console.log(`🎯 Targets generados: ${targets.length}`)
  }

  function initParticles() {
    particles = []
    for (let i = 0; i < totalParticles; i++) {
      const target = targets[i % targets.length]
      const letter = letters[i % letters.length]
      particles.push(new Particle(target.x, target.y, letter))
    }
  }

  function animate() {
    bgCtx.clearRect(0, 0, W, H)
    fgCtx.clearRect(0, 0, W, H)
    particles.forEach(p => {
      p.update()
      p.draw(fgCtx)
    })
    requestAnimationFrame(animate)
  }
  // === Lluvia estilo Matrix ===
const matrixCanvas = document.createElement('canvas')
matrixCanvas.width = W
matrixCanvas.height = H
matrixCanvas.style.position = 'absolute'
matrixCanvas.style.top = '0'
matrixCanvas.style.left = '0'
matrixCanvas.style.zIndex = '-2'
document.querySelector('.stage').appendChild(matrixCanvas)
const mtx = matrixCanvas.getContext('2d')

const lettersMatrix = '01<>[]{};:/*+-LOBO'.split('')
const fontSize = 16
const columns = Math.floor(W / fontSize)
const drops = Array(columns).fill(1)

function drawMatrix() {
  mtx.fillStyle = 'rgba(0, 0, 0, 0.05)'
  mtx.fillRect(0, 0, W, H)
  mtx.fillStyle = '#0F0'
  mtx.font = fontSize + 'px monospace'
  for (let i = 0; i < drops.length; i++) {
    const text = lettersMatrix[Math.floor(Math.random() * lettersMatrix.length)]
    mtx.fillText(text, i * fontSize, drops[i] * fontSize)
    if (drops[i] * fontSize > H && Math.random() > 0.975) drops[i] = 0
    drops[i]++
  }
}
setInterval(drawMatrix, 33)


  const img = document.getElementById('wolfImg')
  img.onload = () => {
    buildTargetsFromImage(img)
    initParticles()
    animate()
  }
})
</script>

<style scoped>
.stage {
  position: absolute; /* en lugar de fixed */
  top: 0;
  left: 0;
  width: 100%;
  height: 100%; /* cubre solo la altura del contenedor padre */
  overflow: hidden;
  pointer-events: none;
  z-index: 0; /* queda detrás del contenido */
}

canvas {
  position: absolute;
  top: 0;
  left: 0;
}
#bgCanvas {
  z-index: 0; /* Lluvia */
}

#fgCanvas {
  z-index: 1; /* Lobo */
}
</style>