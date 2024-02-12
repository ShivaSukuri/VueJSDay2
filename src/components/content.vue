<script setup>
import {ref,reactive} from 'vue';
const inputImportant=ref(false);
const itemName=ref(null);
const itemPrice=ref(null);
    const groceries=reactive([
        {name:"milk",price:30,important:true,found:false},
        {name:"yippee",price:120,important:false,found:false}
    ]);
    const addToCart=()=>{


        let item={
            name:itemName.value,
            price:itemPrice.value,
            important:inputImportant.value,
            found:false
        }
        groceries.push(item);
        console.log(groceries)
        inputImportant.value=false;
    itemName.value=null;
    itemPrice.value=null;


    }
</script>
<template>
<div id="content">
<form @submit.prevent="addToCart">
<label>Product Name
<input type="text" v-model="itemName" required>
</label><br>
<label> Product Price
<input type="number" v-model="itemPrice" required></label><br>
    Important ?<input type="checkbox" v-model="inputImportant" >{{inputImportant}}<br>
<button >AddToCart</button>
</form>
<div>
<ul v-for="item in groceries">
<li :class="{imp1:item.important}" v-on:click="item.found=!item.found" v-show="!item.found">
{{item.name+"  "+item.price}}
</li>
</ul>
</div>

<div id="found">
<ul v-for="item in groceries">
<li :class="{imp1:item.important}" v-on:click="item.found=!item.found" v-show="item.found">
{{item.name+"  "+item.price}}
</li>
</ul>
</div>
</div>


</template>
<style scoped>
#content{
    height:70vh;
    width:20vw;
    background-color:rgb(109, 194, 176);
    border:2px solid black;
    border-radius:5px;

}
.imp1{
    background-color:rgb(191, 160, 73);
}

li{
    background-color:rgb(109, 209, 142);
    border-radius:10px;
}
#found{
    text-decoration:line-through;
    background-color:none;
    margin-top:20px;
}
</style>