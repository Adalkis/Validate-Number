<template>
    <div class="containerNumber">
        <button class="bNumber">{{number}}</button>
    </div>
</template>

<script>


export default {
    name:'buttonNumber',
    props:['number']
}
</script>
<style scoped>
.containerNumber{
   background: gray;
    width: 30px;
    border-radius: 50px;
    height: 30px;
}
</style>