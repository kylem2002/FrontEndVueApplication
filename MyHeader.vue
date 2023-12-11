<template>
<div>
    <h1> {{bookName}} </h1>
    <h4> {{yourName}} </h4>
</div>
</template>

<script>

export default{ // Exporting Default Object
    name: 'MyHeader',
    props:{ 
        bookName:String,
        yourName: String
    }
}

</script>

<style scoped>

div{
    text-align: center;
}

</style>