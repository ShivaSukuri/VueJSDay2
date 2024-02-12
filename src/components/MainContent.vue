<script setup   >
import {ref} from "vue";

const name=ref('');
const result=ref(false);
const email=ref('');
const message = ref("Sukuri Shiva ")
const terms=ref(false);
const submitForm=()=>{
    let res=false;
    if(name.value==="Shiva" && email.value==="Shiva@gmail.com"){
        result.value=true;
    }
    console.log("Name"+name.value);
    console.log("Email"+email.value);
    return res;
}
</script>
<template>
<form @submit.prevent="submitForm">
<div class="content">
Name : 
<input type="text" placeholder="Enter your name" v-model="name" required><br>
Email:
<input type="text" placeholder="Enter your email" v-model="email" required><br>
<!-- <input type="text" :value="message"> -->
<input type="checkbox" v-model="terms" required>     terms and conditions<br>
<button>Submit</button>
<!-- <h1>{{name  +"     "+ email}}</h1> -->
<div class="welcome" v-if="result">
<h1>Welcome Home  {{name}}</h1>
</div>

</div>
</form>


</template>
<style>
*{
    text-align:center;
}
.content{
    height:70vh;
    width:50vw;
    /* background-color:rgb(125, 152, 209); */
    border:2px solid black;
}
</style>
