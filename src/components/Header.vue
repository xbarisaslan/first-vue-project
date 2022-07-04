<template>
    <header>
        <h1>{{title}}</h1>
        <Button text="Add Task" color="rgba(21, 193, 98, 0.8)" />
    </header>
</template>

<script>
import Button from './Button'

 export default {
    name: 'Header',
    props: {
        title: String,
     },
   components: {
    Button,
   }
 }
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: .3rem;
        color:rgba(255, 255, 255, 1)
    }
</style>