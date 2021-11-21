<template>

  <div class="burgers">
    <h3 class="burgertitle"> {{burger.name}} </h3>
    <img class="burgerimage" v-bind:src="burger.url" >
    <ul class="listofallergies">
      <span v-if="burger.gluten == true"> <li> Contains <span class="allergies" > gluten </span></li></span>
      <span v-if="burger.lactose == true"> <li> Contains <span class="allergies" > lactose </span></li></span>
      <span v-if="burger.meat == true"> <li> Contains <span class="allergies" > meat </span></li></span>
      <li> Contains <span class="allergies" > {{burger.kCal}} kCal </span></li>



    </ul>

    <br>
    <div>
    Amount:
    <button v-on:click="decreaseOrder" class="amountbutton" > -</button>
    <button v-on:click="increaseOrder"  class="amountbutton">  +</button>
    {{ amountOrdered }} Orders
  </div>
  </div>


</template>

<script>
export default {
  name: 'Burger',
  props: {
    burger: Object,

  },

  data: function () {
    return {
      amountOrdered: 0,

    }
  },
      methods: {

      decreaseOrder: function (){
        if(this.amountOrdered>0){
          this.amountOrdered-=1;
          console.log(this.amountOrdered, this.burger.name)
          this.$emit('orderedBurgers',{name: this.burger.name, amount: this.amountOrdered});

          //return this.amountOrdered

      }},
      increaseOrder: function (){
        this.amountOrdered+=1;
        console.log(this.amountOrdered, this.burger.name)
        this.$emit('orderedBurgers',{name: this.burger.name, amount: this.amountOrdered});
      }
      }
}




</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.allergies{
  font-weight:bold;
  color: red;

}

.burgers{



}

.burgerimage{
  height: 200px;
  width: 350px;
  max-width: 100%;
  display: block;
  margin: auto;
  border-radius: 20px;

}

.listofallergies{
  margin-left:20%;
}

.burgertitle{
  text-align: center;
}

.amountbutton{
  width: 50px;
  height: 30px;
  font-family: "AppleGothic";
  font-size:15px ;

}

</style>
