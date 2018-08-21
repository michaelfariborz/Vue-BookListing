<template>
    <div>
        <h1>{{title}}</h1>
        <ul>
            <book-item v-for="book in books" :book='book'></book-item>
        </ul>
        <book-form @addBook='appendBook'></book-form>
    </div>
</template>

<script>
import BookItem from './BookItem'
import BookForm from './BookForm'

export default {
    name: 'BookList',
    data() {
        return {
            title: 'All Books',
            books: [
                {id: 1, title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                {id: 2, title: 'American Gods', author: 'Neil Gaiman'},
                {id: 3, title: 'Amusing Ourselves to Death', author: 'Neil Postman'}
            ]
        }
    },
    components: {
        BookItem,
        BookForm
    },
    methods: {
        appendBook(bookTitle, bookAuthor){
            var newId = this.books[this.books.length - 1].id + 1;
            this.books.push({id: newId, title: bookTitle, author: bookAuthor});
        },
        removeBook(id){
            console.log("hello");
            var removeIndex = -1
            for(var index = 0; index < this.books.length; index++){
                if(this.books[index].id == id) {
                    removeIndex = index;
                    console.log("removeIndex = " + removeIndex);
                }
            }
            if(removeIndex >= 0){
                this.books.splice(removeIndex);
            }
        }
    }
}
</script>

<style>
    h1, h2 {font-weight: normal}
    ul {list-style-type: none; padding: 0}
</style>