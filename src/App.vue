<template>
  <div id="app">
    <toggle :currValue="currValue" @ValueChanged="ValueChanged"></toggle>
    {{currValue}}
  </div>
</template>

<script>
import toggle from "@/components/toggle";
export default {
  name: "App",
  components: { toggle },
  data() {
    return {
      currValue: true
    };
  },
  methods: {
    ValueChanged(currValue) {
      this.currValue = currValue;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
