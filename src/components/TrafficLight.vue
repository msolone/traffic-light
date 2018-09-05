<template lang="html">
  <section class="traffic_light">
    <section v-bind:class="{red_light: true, red_live: red_live}">

    </section>

    <section v-bind:class="{yellow_light: true, yellow_live: yellow_live}">

    </section>

    <section v-bind:class="{green_light: true, green_live: green_live}">

    </section>
    <button v-on:click='changeLight'>Change the Light</button>
  </section>
</template>


<script>
export default {
  name: 'TrafficLight',
  data:function() {
    return {
    red_live: false,
    yellow_live: false,
    green_live: false,
    counter: 3
      }
  },
  methods: {
    changeLight:function() {
      if (this.counter % 3 === 0) {
        this.red_live = true
        this.yellow_live = false
        this.green_live = false
        this.counter += 1
        console.log(this.counter)
      } else if (this.counter % 3 === 1) {
        this.red_live = false
        this.yellow_live = true
        this.green_live = false
        this.counter += 1
        console.log(this.counter)
      } else if (this.counter % 3 === 2) {
        this.red_live = false
        this.yellow_live = false
        this.green_live = true
        this.counter += 1
        console.log(this.counter)
      }
      // this.red_live = !this.red_live
      // this.yellow_live = !this.yellow_live
      // this.green_live = !this.green_live
    },
  }
}
</script>

<style scoped lang="css">
.traffic_light {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.red_light {
  background: red;
  opacity: 0.2;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
.yellow_light {
  background: yellow;
    opacity: 0.2;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
.green_light {
  background: green;
  opacity: 0.2;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
.traffic_light button {
  width: 10em;
  height: 5em;
  margin: 2em;
}
.red_live {
  background: red;
  opacity: 1;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
.yellow_live {
  background: yellow;
  opacity: 1;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
.green_live {
  background: green;
  opacity: 1;
  height: 12em;
  width: 12em;
  border-radius: 50%;
}
</style>
