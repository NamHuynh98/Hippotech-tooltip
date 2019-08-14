<template>
  <div class="block" @click="handleClick">
    <div>
      <tooltip v-if="isShowTooltip" :style="{top:coordinatesY,left:coordinatesX}" :color="colorToolTip"></tooltip>
    </div>
  </div>
</template>

<script>
import Tooltip from "@/components/tick/tooltip.vue";
export default {
  name: "Block",
  components: {
    Tooltip
  },
  data() {
    return {
      coordinatesX: "",
      coordinatesY: "",
      state: "none",
      isShowTooltip: false,
      colorToolTip: "#FB7F45"
    };
  },
  props: {},
  methods: {
    handleClick: function(e) {
      if (!this.isShowTooltip) {
        this.coordinatesX = e.offsetX - 30 + "px";
        this.coordinatesY = e.offsetY - 60 + "px";
        this.isShowTooltip = true;
      } else {
        for (let i = 0; i <= e.path.length; i++) {
          if (e.path[i].className == "tooltip") {
            break;
          }
          if (e.path[i].className == "block") {
            this.coordinatesX = e.offsetX - 30 + "px";
            this.coordinatesY = e.offsetY - 60 + "px";
            this.isShowTooltip = true;
            break;
          }
        }
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.block {
  height: 30.5em;
  width: 30%;
  border-radius: 1%;
  margin: 10px auto;
  background-color: #ffffff;
  padding: 30px;
  min-width: 255px;
  position: relative;
}
</style>
