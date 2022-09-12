<script setup>
// const props = defineProps({
//     msg : String
// })

// const emit = defineEmits(['response'])

// emit('response', 'hello from child')
import { reactive, ref } from 'vue';
import image from "../assets/imgs/DRINK-removebg-preview.png"
import burger from "../assets/imgs/amirali-mirhashemian-sc5sTPMrVfk-unsplash.jpg"
import pancake from "../assets/imgs/chad-montano-eeqbbemH9-c-unsplash.jpg"
import wings from "../assets/imgs/erik-mclean-UBtRdqWUbzc-unsplash (1).jpg"
import salad from "../assets/imgs/tania-melnyczuk-xeTv9N2FjXA-unsplash.jpg"
import foot from "../assets/imgs/Opera Snapshot_2022-09-10_213430_www.figma.com.png"

defineProps(['title','num', 'div'])

defineEmits(['burger','pancake', 'del'])

    // const open = ref(false)

    // function toggle(){
    //     open.value = !open.value
    // }

    const openmenu = ref('open')

</script>

<template>
<!-- <div class="nav" >
    <h4>items{{num}}
    </h4>
    <div class="menu" @click="toggle()" >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
            <path d="M24 0C10.7 0 0 10.7 0 24S10.7 48 24 48H76.1l60.3 316.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24-10.7 24-24s-10.7-24-24-24H179.9l-9.1-48h317c14.3 0 26.9-9.5 30.8-23.3l54-192C578.3 52.3 563 32 541.8 32H122l-2.4-12.5C117.4 8.2 107.5 0 96 0H24zM176 512c26.5 0 48-21.5 48-48s-21.5-48-48-48s-48 21.5-48 48s21.5 48 48 48zm336-48c0-26.5-21.5-48-48-48s-48 21.5-48 48s21.5 48 48 48s48-21.5 48-48z"/></svg>

        </div>
<div >
    <img class="logo" :src="image" /></div>
</div>
    <template class="cart" v-if="open">
        <div class="cart" >
{{title||'nothing'}}
        </div>
    </template> -->
<div>
    <h2 class="top" >WEEKEND DEALS</h2>
</div>

    <div class="items" >

        <div class="row" >
<div class="food" id="1" >
    <img class="menu-icon" :src="burger" alt="">
    <h2 class="name" >Cheese Burger</h2>
    <p2 class="price" ><b>₦1,500</b></p2>
<br>
<button class="addcart" @click="$emit('burger')" >ADD TO CART</button>
</div>

<div class="food" id="2" >
    <img class="menu-icon" :src="pancake" alt="">
    <h2 class="name" >Pancake</h2>
    <p2 class="price" ><b>₦800</b></p2>
<br>
<button class="addcart" @click="$emit('pancake')"  >ADD TO CART</button>
</div>
</div>
<br>
<div class="row" >
<div class="food" id="3" >
    <img class="menu-icon" :src="wings" alt="">
    <h2 class="name" >Chicken Wings</h2>
    <p2 class="price" ><b>₦1,200</b></p2>
<br>
<button class="addcart" >ADD TO CART</button>
</div>
<div class="food" id="4" >
    <img class="menu-icon" :src="salad" alt="">
    <h2 class="name" >Beef Salad</h2>
    <p2 class="price" ><b>₦1,000</b></p2>
<br>
<button class="addcart" >ADD TO CART</button>
</div>
</div>
    </div>

    <div class="footer" >
<img class="foot" :src="foot" alt="">
    </div>
    <!-- <h1>{{msg|| 'Nothing'}}</h1> -->
</template>


<style scoped>

    .foot{
        width: 300px;
        height: 300px;
    }



    .cart{
        width: 100%;
        height: 600px;
        background-color: #ffffff;
        z-index: 2;
        color: black;
        font-size: 23px;
    }

    .top{
        font-weight: 400;
font-size: 50px;
line-height: 61px;
margin-top: 60px;
margin-bottom: 20px;
color: #C283CB;
    }

    .food{
        padding: 5px;
        width: fit-content;
        background-color: #FFFFFF;
        margin-right: 20px;
    }

.row{
    display: flex;
    flex-direction: row;
}

    .name{
        font-weight: 400;
font-size: 20px;
    }

    .price{
        font-weight: 1600;
font-size: 15px;
    }

    .addcart{
        background: #72B8FF;
border: 1px solid #FFFFFF;
border-radius: 10px;
color: #FFFFFF;
font-weight: 800;
font-size: 10px;
padding: 10px;
    }

    .menu-icon{
        width: 150px;
height: 100px;
    }

    .items{
        width: fit-content;
        margin: 0;
    }

    body{
        height: 100%;
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

    .side-bar{
        background-color: #008DFF;
        border-radius: 0px 35px 0px 0px;
        height: 100%;
        width: 80%;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        overflow-x: hidden;
        overflow-y: hidden;
        transition: 0.5s;
    }
    .profile-cont{
        color: #ffffff;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding-top: 160px;

}
    .username{
        font-weight: 600;
        font-size: 32px;
        font-family: 'Inter';
font-style: normal;
font-weight: 600;
line-height: 39px;
color: #ffffff;
}
    .tasks, .comp-tasks{
        font-weight: 600;
        font-size: 20px;
        font-family: 'Inter';
font-style: normal;
font-weight: 600;
}
.setting{
    margin-top: 155%;
    margin-left: 85%;
}
.white{
    fill: #ffffff;
    width: 35px;
height: 35px;
}

.menu{
    width: 20px;
height: 30px;
fill: #C283CB;
margin-top: 20px;
margin-right: 15px;
float: right;
}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    overflow: hidden;
}
</style>