<template>
  <div id="orders">
    <div id="orderList">
      <div v-for="(order, key) in orders" v-bind:key="'order'+key">
        <span> #{{key}} </span>
        <br>
        <span> Burgers ordered: {{order.orderItems}} </span>
        <br>
        <span> Gender: {{order.form.gender}} </span>
        <br>
        <span> Name: {{order.form.fn}}  </span>
        <br>
        <span> Email: {{order.form.en}}</span>
        <br>
        <span>Payment: {{order.form.selected}} </span>
        <br> <br>



<!--      #{{ key }}: {{ order.orderItems.join(", ") }}-->
      </div>
      <button v-on:click="clearQueue">Clear Queue</button>
    </div>
    <div id="dots">
        <div v-for="(order, key) in orders" v-bind:style="{ left: order.details.x + 'px', top: order.details.y + 'px'}" v-bind:key="'dots' + key">

          {{ key }}

        </div>
    </div>
  </div>
</template>
<script>


import io from 'socket.io-client'
const socket = io();

export default {
  name: 'Dispatcher',
  data: function () {
    return {
      orders: null
    }
  },
  created: function () {
    socket.on('currentQueue', data =>
      this.orders = data.orders);
  },
  methods: {
    clearQueue: function () {
      socket.emit('clearQueue');
    }
  }
}
</script>
<style>
#orderList {
  top:1em;
  left:1em;
  position: absolute;
  z-index: 2;
  color:black;
  background: rgba(255,255,255, 0.5);
  padding: 1em;
}
#dots {
  position: relative;
  margin: 0;
  padding: 0;
  background: url(/img/polacks.jpg);
  background-repeat: no-repeat;
  width:1920px;
  height: 1078px;
  cursor: crosshair;
}

#dots div {
  position: absolute;
  background: black;
  color: white;
  border-radius: 10px;
  width:20px;
  height:20px;
  text-align: center;
}
</style>
