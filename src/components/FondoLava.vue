<template>
  <div class="fondo-lava">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      version="1.1"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      xmlns:svgjs="http://svgjs.dev/svgjs"
      viewBox="0 0 1440 560"
      preserveAspectRatio="xMidYMid slice"
    >
      <defs>
        <clipPath id="rounded-corners">
          <rect x="0" y="0" width="1440" height="560" rx="40" ry="40" />
        </clipPath>
      </defs>
      <g clip-path="url(#rounded-corners)" fill="none">
        <rect width="1440" height="560" fill="#0a2e1a" />
        <path d="M903.38 283.49a181.24 181.24 0 1 0 362.48 0a181.24 181.24 0 1 0 -362.48 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M279.879 167.698L238.397 288.17 358.87 329.65 400.352 209.18z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M1268.929 183.631L1289.539 77.604 1120.194 99.703z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M730.558 437.13L691.83 324.656 579.356 363.384 618.084 475.857z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M530.96 362.69a169.52 169.52 0 1 0 339.04 0a169.52 169.52 0 1 0 -339.04 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M1121.19 308.156L1178.84 222.687 1035.722 250.506z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M345.21 448.21a122.86 122.86 0 1 0 245.72 0a122.86 122.86 0 1 0 -245.72 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M204.735 427.649L303.46 585.977 382.535 443.322z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M130.75 7.21a172.48 172.48 0 1 0 344.96 0a172.48 172.48 0 1 0 -344.96 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M231.012 193.514C247.329 192.833 261.197 181.968 268.505 167.363C275.099 154.185 271.764 139.202 264.647 126.298C257.214 112.822 246.37 100.377 231.012 99.386C214.071 98.292 197.721 106.9 188.909 121.409C179.758 136.477 178.788 155.513 187.677 170.737C196.497 185.842 213.536 194.243 231.012 193.514"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M1105.537 388.276L1168.626 401.686 1157.196 300.349z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M89.126 65.726L-28.152 147.845 53.967 265.123 171.245 183.004z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M-136.98 209.92a181.37 181.37 0 1 0 362.74 0a181.37 181.37 0 1 0 -362.74 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
      </g>
    </svg>
  </div>
</template>

<script>
export default {
  name: "FondoLava",
};
</script>

<style scoped>
.fondo-lava {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 0;
  border-radius: 40px;
}

svg {
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
}

/* Animaciones suaves */
@keyframes float1 {
  0% { transform: translate(0, 0); }
  50% { transform: translate(-10px, 0); }
  100% { transform: translate(0, 0); }
}
.triangle-float1 {
  animation: float1 5s infinite ease-in-out;
}

@keyframes float2 {
  0% { transform: translate(0, 0); }
  50% { transform: translate(-5px, -5px); }
  100% { transform: translate(0, 0); }
}
.triangle-float2 {
  animation: float2 4s infinite ease-in-out;
}

@keyframes float3 {
  0% { transform: translate(0, 0); }
  50% { transform: translate(0, -10px); }
  100% { transform: translate(0, 0); }
}
.triangle-float3 {
  animation: float3 6s infinite ease-in-out;
}

/* === Ajustes responsive === */
@media (max-width: 768px) {
  .fondo-lava {
    border-radius: 20px;
  }

  svg {
    width: 120%;
    height: 100%;
  }
}

@media (max-width: 480px) {
  .fondo-lava {
    border-radius: 10px;
  }

  svg {
    width: 140%;
    height: 110%;
  }
}
</style>
