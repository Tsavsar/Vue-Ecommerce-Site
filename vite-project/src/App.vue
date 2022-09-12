<script setup>
  import { ref } from 'vue';
import Childcomponent from './components/childcomponent.vue';
import image from "./assets/imgs/DRINK-removebg-preview.png"



const items = ref([
  { id: 1, name: 'Chicken' },
  { id: 2, name: 'Ice' },
  { id: 3, name: 'Wing' }
])

const posts = ref([

])


function deletearr() {

post.id>1;
}
function removepost(todo) {
  posts.value = posts.value.filter((t) => t !== todo)
}


const open = ref(false)

    function toggle(){
        open.value = !open.value
    }
// const function = item => {

// }






// const message= ref('Hello bro')

// const childMsg = ref('No child msg yet')
  // // const counter = reactive({count: 0})
  // const count = ref(0)

  // function increment(){
  //   count.value++
  // }
  // function dec(){
  //   count.value--
  // }

  // const text= ref ('')

  // const yeat = ref(true)

  // function toggle(){
  //   yeat.value = !yeat.value
  // }

  // const col = ref(true)

  // function change(){
  //   col.value = !col.value
  // }
  // // const message = ref ('hello world')
  // const titleclass = ref ('title')

  // let id = 0

  // const newtodo = ref('')
  // const hidecom = ref(false)
  // const todos= ref([
  //   { id:id++ , text: 'learn JS', done: true},
  //   { id:id++ , text: 'learn Html', done: false},
  //   { id:id++ , text: 'learn CSS', done: false}

  // ])

  // //now we will filter t.done
  // const filteredtodos = computed(() => {
  //   return hidecom.value
  //   ? todos.value.filter((t) => !t.done)
  //   : todos.value
  // })

  // function addtodo(){
  //   todos.value.push({id: id++, text: newtodo.value})
  //   newtodo.value=''
  // }

  // function remove(todo){
  //   todos.value = todos.value.filter((t)=> t !==todo)

//     The filter function filters all the words in the array which have length greater than 5

// var words = ["hi", "hello", "hey", "apple", "watermelon",
//             "lemon", "javascript"];
// var result = words.filter(word => word.length > 5);
// console.log(result);
// Output :

// [ 'watermelon', 'javascript' ]
//   }

// const heartclass = ref('like')

// const heart = ref(false)

// function like(){
//   heart.value = !heart.value
// }
</script>


<template>
  <div class="nav" >
    <div class="menu" @click="toggle()" >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
            <path d="M24 0C10.7 0 0 10.7 0 24S10.7 48 24 48H76.1l60.3 316.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24-10.7 24-24s-10.7-24-24-24H179.9l-9.1-48h317c14.3 0 26.9-9.5 30.8-23.3l54-192C578.3 52.3 563 32 541.8 32H122l-2.4-12.5C117.4 8.2 107.5 0 96 0H24zM176 512c26.5 0 48-21.5 48-48s-21.5-48-48-48s-48 21.5-48 48s21.5 48 48 48zm336-48c0-26.5-21.5-48-48-48s-48 21.5-48 48s21.5 48 48 48s48-21.5 48-48z"/></svg>
 <div class="badge" >{{posts.length}}</div> 
        </div>
<div >
    <img class="logo" :src="image" /></div>
</div>
    <template class="cart" v-if="open">
        <div class="cart" >
          <div class="rec" >
<ul >
  <li v-for="post in posts" >
    {{post.title}} ------ ₦{{post.price}}
    <br>
    <br>
  </li>    <button class="addcart" @click="posts.splice(0, posts.length)" >Clear Cart</button>

</ul>
<div class="total" >
  <div v-for="prices in posts.price" >Total ------ {{prices.price.sum}}</div>
</div>
</div> </div>
    </template>


<Childcomponent :num="posts.length"
@burger="posts.push({id: 1, title:'Burger', price: 1500})"
@pancake="posts.push({id: 2, title:'pancake', price:800})"
>
</Childcomponent>



<!-- <form @submit.prevent="addtodo()">
  <input v-model="newtodo" type="text">
<button>Add Todo</button>
</form>
<br>
<button @click="heart = !heart">
  <h1 v-if="heart" :class="heartclass">I like this</h1>
<h1 v-else>I don't like this</h1>

</button>


<br>
<ul>
  <li v-for="todo in filteredtodos" :key="todo.id" >
    <input type="checkbox" v-model="todo.done">
    <span :class="{ done: todo.done }">{{ todo.text }}</span>
    <button @click="remove(todo)">X</button>
  </li>
</ul>
<button @click="hidecom = !hidecom">
  {{ hidecom ? 'Show all' : 'Hide com' }}
</button> -->
<!--
<br>
  <br>
<h1 v-if="col" :class="titleclass" > yo bro </h1>
<h1 v-else > yo bro </h1>

<button @click="change">^</button>
<br>
<br>
<p>The Count is: {{counter.count}}</p>
<input v-model="text" placeholder="Type here" type="text">
<br>
<button @click="increment" > the value is : {{count}}</button>
<button @click="dec"> -</button>


<p>{{text}}</p>

<br>
<br>
<br>


<button @click="toggle">toggle</button>
<h1 v-if="yeat" > Yeat makes bangers </h1>
<h1 v-else > Yeat still makes bangers </h1>
 -->

</template>

<style>

  .badge{
    width: fit-content;
    height: fit-content;
    color: #FFFFFF;
    background-color: #F8A431;
    border-radius: 50%;
    padding-left: 8px;
    padding-right: 8px;
  }

  .addcart{
    background: #72B8FF;
border: 1px solid #FFFFFF;
color: #FFFFFF;
font-weight: 800;
font-size: 10px;
padding: 10px;
width: 100px;
}
  ul{
    padding-top: 60px;
    display: flex;
    flex-direction: column;
  }

  li{
    text-decoration: none;
    list-style: none;
    
  }


.menu{
  width: 20px;
height: 30px;
fill: #C283CB;
margin-top: 20px;
margin-right: 15px;
float: right;
}


  .nav{
    top: 0;
    flex-direction: row;
}

.logo{
    float: left;
    width: 60px;
    top:0;
    height: 60px;
}

  body {
    margin: 0;
    width: 100%;
    height: 100%;
    background-color: #C0E0FF;
    overflow-x: hidden;
    overflow-y: scroll;

    padding: 20px;
    z-index: 0;
  }

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.cart{
  width: 100%;
  height: fit-content;
  background-color: #ffffff;
  z-index: 2;
  color: black;
  font-size: 23px;
}


</style>