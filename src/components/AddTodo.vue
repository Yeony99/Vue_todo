<template>
    <div>
        <form @submit="addTodo"> <!--v-on-->
            <input type="text" v-model="title" name="title">
            <button type="submit">Add</button>
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: 'AddTodo',
    data() {
        return {
            title: '',
        };
    },
    methods: {
        addTodo(e) {
            e.preventDefault();

            const newTodoObj = {
                id: uuid.v4(),
                title : this.title, 
                //바인딩된 데이터
                completed: false,
            }
            this.$emit('add-todo', newTodoObj); 
            //$ emit('발생시킬 이벤트', 넘길 데이터)
            this.title =''; 
            //전송한 뒤에 title 비우기
        }
    },
};
</script>
<style scoped>

</style>