<template>
    <li>{{book.id}}: {{book.title}}:{{book.author}} <button v-on:click="bookRemove(book.id)">Remove</button></li>
</template>

<script>
export default {
    name: 'BookItem',
    props: ['book'],
    methods:
    {
        bookRemove(id){
            this.$emit('removeBook', id);
        }
    }
}
</script>

<style>
li {display: block; margin: 0 10px}
</style>