<template>
    <p class="m-5 p-5 text-left rounded-lg shadow-sm">
        <input type="checkbox" name="todo" id="todo" class="mr-2 leading-tight" @change="markDone">
        <span :class="{'iscompleted': todo.completed }">{{ todo.title }}</span>
        <button class="float-right" @click="$emit('delete-item', todo.id)">X</button>
    </p>    
</template>

<script>
    export default {
        name: "Todo",
        props: ['todo'],
        methods: {
            markDone() {
                this.todo.completed = !this.todo.completed
            }
        },
    }
</script>

<style  scoped>

p{
    background: #ffffff;

}
.iscompleted{
    text-decoration-line: line-through;
}
button{
    background: red;
    color: #ffffff;
    padding: 0 5px;
}

</style>