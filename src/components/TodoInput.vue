<template lang="html">
    <div>
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
        <button v-on:click="addTodo">추가</button>
    </div>
</template>

<script lang="javascript">
export default {
    data() {
        return {
            newTodoItem: ''
        }
    },
    methods: { 
        addTodo() {
            if (this.newTodoItem !== '') {
                var value = this.newTodoItem && this.newTodoItem.trim();
                this.$emit('addTodo', value);
                this.clearInputbox();
            }
        },

        clearInputbox() {
            this.newTodoItem = '';
        }
    }
}
</script>

<style lang="css">
    
</style>