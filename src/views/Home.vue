
<template>

  <div id="header">
    <img src="https://thatsup.se/content/img/article/11/apr/uppsalas-b%C3%A4sta-barer.jpg" id="headerimage">
    <h1 id="welcome">Welcome to BurgerHeaven</h1>
  </div>
  <div >
    <h2>Pick your burgers here</h2>
    <div class="wrapperburger">
      <Burger v-for="burger in burgers"
              v-bind:burger="burger"
              v-bind:key="burger.name"
              v-on:orderedBurgers="addToOrder($event)"/>
  </div>
  </div>
  <h2> Customer information </h2>
  This is where you provide necessary information

  <h3> Delivery information </h3>

  <div id="backgroundform">

  <form>
    <p>
      <label for="fullname"> Full name </label><br>
      <input type="text" id="fullname" v-model="fn" required="required" placeholder="First - and Last name">
<!--     <span> Typed: {{ fn }}</span>-->
    </p>
    <p>
      <label for="emailadress"> E-mail </label><br>
      <input type="email" id="emailadress" v-model="en" required="required" placeholder="E-mail address ">
<!--      <span> Typed:{{en}}</span>-->
    </p>
<!--    <p>
      <label for="streetname"> Street </label><br>
      <input type="text" id="streetname" v-model="st" required="required" placeholder="Street name">
&lt;!&ndash;      <span> Typed:{{st}}</span>&ndash;&gt;
    </p>
    <p>
      <label for="house"> House </label><br>
      <input type="number" id="house" v-model="house" required="required" placeholder="House number">
&lt;!&ndash;      <span> Typed:{{house}}</span>&ndash;&gt;
    </p>-->


    <div id="v-model-select" class="payment">
      <label> Payment method </label>
      <select v-model="selected" >
        <option> Swish </option>
        <option> Creditcard </option>
        <option selected="selected"> Klarna </option>
        <option> Banktranfer </option>

      </select>
<!--      <span> Selected: {{ selected }}</span>-->
    </div>

<br>

    <legend> Gender </legend>

    <input type="radio" id="male" v-model="gender" value="Male">
    <label for="male"> Male </label><br>
    <input type="radio" id="female" v-model="gender" value="Female">
    <label for="female"> Female </label><br>
    <input checked="checked" type="radio" id="nogender" v-model="gender" value="Do not wish to provide">
    <label for="nogender"> Do not wish to provide  </label><br>
<!--    <span> Selected: {{ gender }}</span>-->
  </form>

    <div class="scrollmap">
      <div id="map" v-on:click="setLocation" >
          <div id="dots">
          <div  v-bind:style="{ left: location.x +'px', top: location.y +'px'}"  >

        T
          </div>
      </div>

    </div>
    </div>
  </div>




  <button v-on:click="submitorder(key)">
    <img src="https://cdn.pixabay.com/photo/2013/07/12/17/40/checkbox-152185_960_720.png" width="50px">
    Send info
  </button>



  <footer>
    <hr> &copy; Thank you for ordering with us!
  </footer>



<!--
  <main>
    <section id="backgroundburger">
      <div class="wrapper">


        <div class="burger1">
          <h3> The Bruno burger</h3>
          <img src="https://images.unsplash.com/photo-1571091718767-18b5b1457add?ixid=MnwxMjA3fDB8MHxzZWF
                    yY2h8Nnx8YnVyZ2VyfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&w=1000&q=80" height="200px" >

          <ul>
            <li> Contains <span class="allergies" > Lactose </span></li>
            <li> Contains <span class="allergies" > Gluten </span></li>
            <li> Contains <span class="allergies" > Nuts </span></li>
          </ul>
        </div>


        <div class="burger2" >
          <h3> Momo meadow </h3>
          <img src="https://media.dagensps.se/app/uploads/2020/05/12153609/hamburgare.jpg" height="200px" >
          <ul>
            <li> Contains <span class="allergies" > Pickles </span></li>
            <li> Contians <span class="allergies" > Sorrel mayonnaise </span></li>
          </ul>
        </div>


        <div class="burger3">
          <h3> The beyond burger </h3>
          <img   src="https://assets.epicurious.com/photos/5c745a108918ee7ab68daf79/5:4/w_3129,h_2503,c_limit/Smashburger-recipe-120219.jpg" height="200px"  >
          <ul>
            <li> Contains <span class="allergies" > Vegan patty </span></li>
            <li>Contains <span class="allergies" > Gluten </span> </li>
          </ul>
        </div>
      </div>

    </section>



&lt;!&ndash;    <section style="clear:left"  id="backgroundform">&ndash;&gt;

&lt;!&ndash;      <form>
        <p>
          <label for="fullname"> Full name </label><br>
          <input type="text" id="fullname" name="fn" required="required" placeholder="First - and Last name">
        </p>
        <p>
          <label for="emailadress"> E-mail </label><br>
          <input type="email" id="emailadress" name="em" required="required" placeholder="E-mail address ">
        </p>
        <p>
          <label for="streetname"> Street </label><br>
          <input type="text" id="streetname" name="st" required="required" placeholder="Street name">
        </p>
        <p>
          <label for="house"> House </label><br>
          <input type="number" id="house" name="house" required="required" placeholder="House number">
        </p>


        <p>
          <label> Payment method </label>
          <select id="payment" name="pay" >
            <option > Swish </option>
            <option> Creditcard </option>
            <option selected="selected"> Klarna </option>
            <option> Banktranfer </option>
          </select>

        </p>


          <legend> Gender </legend>
          <input type="radio" id="male" name="gender" value="Male">
          <label for="male"> Male </label><br>
          <input type="radio" id="female" name="gender" value="Female">
          <label for="female"> Female </label><br>
          <input checked="checked" type="radio" id="nogender" name="gender" value="Do not wish to provide">
          <label for="nogender"> Do not wish to provide  </label><br>

      </form>&ndash;&gt;

&lt;!&ndash;    </section>&ndash;&gt;

  </main>
  <br/>-->



</template>

<script>
import Burger from '../components/Burger.vue'
import io from 'socket.io-client'
import menu from '../assets/menu.json'


const socket = io();

/*function MenuItem(name, url, kCal, lactose, gluten) {
  this.name= name;
  this.url=url;
  this.kCal=kCal;
  this.lactose=lactose;
  this.gluten=gluten;
}

const burger1= new MenuItem('The Bruno Burger', "https://images.unsplash.com/photo-1571091718767-18b5b1457add?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Nnx8YnVyZ2VyfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&w=1000&q=80" , 300, false,  true);
const burger2= new MenuItem('Momo meadow', "https://media.dagensps.se/app/uploads/2020/05/12153609/hamburgare.jpg" , 200, true,  true);
const burger3= new MenuItem('The beyond burger', "https://assets.epicurious.com/photos/5c745a108918ee7ab68daf79/5:4/w_3129,h_2503,c_limit/Smashburger-recipe-120219.jpg" , 250, true,  false);

const allBurgers=[burger1, burger2, burger3];

console.log(allBurgers);*/

export default {
  name: 'Home',
  components: {
    Burger
  },
  data: function () {
    return {
      burgers: menu,
      selected: "Klarna",
      gender: "Do not wish to provide",
      fn: "",
      en: "",
      /*st:"",
      house:"",*/
      orderedBurgers: {},
      location: {
        x: 0,
        y: 0
      }

    }
  },


  methods: {
    getOrderNumber: function () {
      return Math.floor(Math.random() * 100000);
    },
    addToOrder: function (event) {
      return this.orderedBurgers[event.name] = event.amount;
    },


    addOrder: function () {
      // var offset = {
      //   x: event.currentTarget.getBoundingClientRect().left, //Han ändrade från var till let :)
      //   y: event.currentTarget.getBoundingClientRect().top
      // };

 /*     socket.emit("addOrder", {
        orderId: this.getOrderNumber(),
        details: {
          x: event.clientX - 10 - offset.x,
          y: event.clientY - 10 - offset.y
        },
        orderItems: ["Beans", "Curry"],
        /!*orderedBurgers: this.addToOrder(),*!/
        form: [this.gender, this.fn, this.en, this.selected, this.orderedBurgers]
      });*/
      // this.location = {x: event.clientX - 10 - offset.x, y: event.clientY - 10 - offset.y}

    },
    submitorder: function () {

      socket.emit("addOrder", {
            orderId: this.getOrderNumber(),
            details: {
                       x: this.location.x,
                       y: this.location.y
                      },
            orderItems: this.orderedBurgers,
            form: {
                   gender: this.gender,
                    fn: this.fn,
                    en: this.en,
                    selected: this.selected,
            }
    },
        // console.log(this.gender, this.fn, this.en , this.selected, this.orderedBurgers)

      )},

          setLocation:function (event) {
        var offset = {
          x: event.currentTarget.getBoundingClientRect().left, //Han ändrade från var till let :)
          y: event.currentTarget.getBoundingClientRect().top
        };
        this.location = {x: event.clientX - 10 - offset.x, y: event.clientY - 10 - offset.y}
      },



    }
  }

</script>

<style>



  #map {
    width: 1920px;
    height: 1078px;
    background: url("/img/polacks.jpg");
  }


  .scrollmap{
    height: 500px;
    width: 500px;
    overflow: scroll;
  }




  body{
    font-family: "AppleGothic";
    font-size:20px ;
  }



  #backgroundburger{
    background-color: black;
    color:white

  }

  button:hover {
    background-color: pink;
    cursor: pointer;
  }

  button{
    margin: 10px
  }

  #backgroundform{
    background-color: beige;
    border: 2px dotted black;
    border-radius: 10px;
    color: black;
    display: grid;
    grid-template-columns: 50% 50%;
    grid-template-rows: 100%;

  }

  section{
    margin-left: 5px;
    margin-right: 5px;
    border-radius: 30px;
  }

  #header{
    margin-left: 5px;
    margin-right: 5px;
    height: 400px;
    overflow: hidden;
    border-radius: 30px;

  }

  #welcome{
    position: absolute;

    margin-top: -600px;
    margin-left: 5px;
  }

  #headerimage{
    height: auto;
    width: 100%;
    opacity: 50%;
  }

  .wrapper{
    display: grid;
    grid-gap: 40px;
  }
  .burgerheadline{
    grid-column: 1 /span 3;
    grid-row: 1;
    margin-left: 20px;
  }

  .burger1{
    grid-column: 1 ;
    grid-row: 2;
    margin:10px;
  }

  .burger2{
    grid-column: 2 ;
    grid-row: 2;
    margin:10px;
  }

  .burger3{
    grid-column: 3;
    grid-row: 2;
    margin:10px;
  }

  .wrapperburger{
    display: grid;
    grid-template-columns: 33% 33% 33%;
    grid-template-rows: 100%;
    grid-gap: 10px;
    background-color: beige;
    border-radius: 20px;
  }


  #dots div{
    position: relative;
    background: black;
    color: white;
    border-radius: 10px;
    width:20px;
    height:20px;

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







</style>
