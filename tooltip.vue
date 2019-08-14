<template>
  <div class="tooltip">
    <svg
      height="60"
      width="100"
      xmlns="http://www.w3.org/2000/svg"
      preserveAspectRatio="none"
      :fill="color"
    >
      <path
        d="
            M 0 0 
            L 100 0
            L 100 50
            L 40 50
            L 30 60
            L 20 50
            L 0 50
            L 0 0
            Z"          
      />Sorry, your browser does not support inline SVG.
    </svg>
  </div>
</template>

<script>
export default {
  name: "Tooltip",
  props: {
    color: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.tooltip {
  position: absolute;
  svg {
    filter: drop-shadow(3px 3px 2px rgba(209, 203, 203, 0.61));
  }
}
</style>
