<script setup lang="ts">
  import index from "@/components/index.vue";
  import header2 from "@/components/header2.vue";
  import content from "@/components/content.vue";
  import MainContent from "@/components/MainContent.vue";
</script>

<template>
<div>
<index ></index>
</div>

<div>
<content class="content-1"/>
</div>

<div>
<content class="content-2"/>
</div>
<div>
<MainContent class="main-content"/>
</div>

<div>
<index class="footer"/>
</div>
</template>

<style scoped>
.content-1{
  position:absolute;
    top:100px;
    left:10px;
    margin-top:20px;
}
.content-2{
 position:absolute;
    top:100px;
    right:10px;
        margin-top:20px;
}
.main-content{
  position:absolute;
  top:120px;
  left:24vw;
  }


.footer{
  position:absolute;
  bottom:100px;
  left:0px;
  margin-bottom:20px;
}
</style>
