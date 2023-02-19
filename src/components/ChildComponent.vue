<template>
    <div>
        <h1>Child Component</h1>
        <h4>simple data transfered from home to child component is {{name}}</h4>
        <h4>object transfered from home to child component is {{users[0].name}}</h4>
        <button v-on:click="getName('Charul')">Call Function</button>
    </div>
</template>
<script>
export default{
    name:'Child',
    props:{
        name:String,
        users:Array,
        getName:Function,
    }
}
</script>
