<template>
    <div class="todo-card">
        {{ todoObject.todo }}
    </div>
</template>

<script>
export default {
    name: 'todo-card',
    props: ['todoObject']
}
</script>

<style scoped>
.todo-card {
    border-radius: 5px;
    box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.4);
    padding: 5px 10px;
    margin: 20px 0;
}
</style>