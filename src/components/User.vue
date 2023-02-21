<template>
    <div class="users">
        <h1>{{data.name}}</h1>
        <h1>{{data.email}}</h1>
        <button v-on:click="getName(data.name)">Alert Name</button>
    </div>
</template>
<script>
export default{
    name:'User',
    props:{
        data:Object,
        getName:Function
    },
    // methods:{
    //     getName(name){
    //         alert(name);
    //     }
    // }
}
</script>
<style scoped>
    .users{
        background-color: skyblue;
        border-bottom: 1px solid;
        margin: 2px;
        padding-left: 10px;
        padding-bottom: 5px;
    }
</style>