<template>
    <li>{{book.id}}: {{book.title}}:{{book.author}} <button v-on:click="remove(book.id)">Remove</button></li>
</template>

<script>
export default{
    name: 'BookItem',
    props: ['book'],
    methods:
    {
        remove(id){
            this.$emit('removeBook', id);
        }
    }
}
</script>

<style>
li {display: block; margin: 0 10px}
</style>