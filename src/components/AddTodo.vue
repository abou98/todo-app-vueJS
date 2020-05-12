<template>
    <section>
        <form @submit="addTodo" class="flex justify-center mx-auto">
            <input type="input" v-model="title" class="mr-2 leading-tight p-4 rounded">
            <button type="submit" class="pd-10">Add</button>
        </form>
        
    </section>
</template>
<script>
    export default {
        name: "AddTodo",
        data() {
            return {
                title: ''
            }
        },
    methods: {
        addTodo(e) {
            e.preventDefault()
            const todo = {
                id: 4,
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', todo);
            this.title = '';
        }
    },    

    }
</script>

<style scoped>
form{
    width: 90%;

}
button{
    background: green;
    color: #ffffff;
    padding: 5px 10px;
}

</style>