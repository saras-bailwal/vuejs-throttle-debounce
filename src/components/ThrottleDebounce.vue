<template>
  <div class="hello">
    <div>
      <span>Raw: {{ raw }}</span>
      <br />
      <span>Throttle: {{ throttle }}</span>
      <br />
      <span>Debounce: {{ debounce }}</span>
    </div>

    <div class="funbox" @mousemove="updateRaw();updateThrottle();updateDebounce();"></div>
  </div>
</template>

<script>
import _ from 'lodash'

export default {
  name: "ThrottleDebounce",
  data() {
    return {
      raw: 0,
      throttle: 0,
      debounce: 0
      }
  },
  methods: {
    updateRaw() {
      this.raw++;
    },
    updateThrottle: _.throttle(function () {
      this.throttle++
    }, 1000),
    updateDebounce: _.debounce(function () {
      this.debounce++
    }, 500)
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.funbox {
  height: 200px;
  width: 300px;
  box-sizing: border-box;
  color: blue;
  border: 1px solid;
  background-color: antiquewhite;
}
</style>
