<template>
  <div class="control" :class="{'false': !currValue, 'true': currValue}" @click="Toggle()">
    <div class="button"></div>
  </div>
</template>

<script>
export default {
  props: {
    currValue: Boolean,
    required: false,
    default: false
  },
  methods: {
    Toggle() {
      this.currValue = !this.currValue;
      this.$emit("ValueChanged", this.currValue);
    }
  }
};
</script>
<style scoped>
.control {
  height: 15px;
  width: 30px;
  background-color: #DDD;
  border-radius: 7px;
  position: relative;
  cursor: pointer;
  margin: 10px;
}
.control .button {
  position: absolute;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  transition: left 0.2s, background-color 0.2s;
}

.control.true .button {
  background-color: #0072bc;
  left: 100%;
}

.control.false .button {
  background-color: #999;
  left: 0;
}
</style>
