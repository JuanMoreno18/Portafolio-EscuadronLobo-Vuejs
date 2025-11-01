<template>
  <div class="fondo-lava">
    <svg xmlns="http://www.w3.org/2000/svg" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink"
      xmlns:svgjs="http://svgjs.dev/svgjs" viewBox="0 0 1440 560">
      <defs>
        <clipPath id="rounded-corners">
          <rect x="0" y="0" width="1640" height="680" rx="40" ry="40"/>
        </clipPath>
      </defs>
      <g clip-path="url(#rounded-corners)" fill="none">
        <rect width="1440" height="560" x="0" y="0" fill="#0a2e1a"></rect>
        <path d="M903.38 283.49 a181.24 181.24 0 1 0 362.48 0 a181.24 181.24 0 1 0 -362.48 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M279.87931496450886 167.6976390055248L238.39724239518821 288.1703253898837 358.8699287795472 329.6523979592044 400.3520013488678 209.17971157484544z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M1268.9292631036747 183.63102030060372L1289.5388120075734 77.60408271971517 1120.1936311842912 99.70322815431143z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M730.5578276754125 437.1295284122104L691.8299594839084 324.655632341249 579.3560634129469 363.38350053275303 618.083931604451 475.85739660371445z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M530.96 362.69 a169.52 169.52 0 1 0 339.04 0 a169.52 169.52 0 1 0 -339.04 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M1121.1904984662337 308.15568256605195L1178.8399030516562 222.68692546970541 1035.7217413698872 250.50627798062965z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M345.21 448.21 a122.86 122.86 0 1 0 245.72 0 a122.86 122.86 0 1 0 -245.72 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M204.73533685134262 427.64888599953736L303.46011736347907 585.9771228187643 382.5353254701889 443.32167113623353z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M130.75 7.21 a172.48 172.48 0 1 0 344.96 0 a172.48 172.48 0 1 0 -344.96 0z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M231.012,193.514C247.329,192.833,261.197,181.968,268.505,167.363C275.099,154.185,271.764,139.202,264.647,126.298C257.214,112.822,246.37,100.377,231.012,99.386C214.071,98.292,197.721,106.9,188.909,121.409C179.758,136.477,178.788,155.513,187.677,170.737C196.497,185.842,213.536,194.243,231.012,193.514"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float3" />
        <path d="M1105.5373368611104 388.2762266109683L1168.6255722658527 401.68604501042927 1157.1961821626728 300.34878270358513z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float2" />
        <path d="M89.12610078752635 65.72571453621863L-28.15208138414812 147.84478176035668 53.966985839989945 265.12296393203115 171.24516801166442 183.0038967078931z"
          fill="rgba(0, 255, 136, 0.15)" class="triangle-float1" />
        <path d="M-136.98 209.92 a181.37 181.37 0 1 0 362.74 0 a181.37 181.37 0 1 0 -362.74 0z"
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
  width: 180%;
  height: 120%;
  display: block;
}

/* Animaciones */
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
</style>