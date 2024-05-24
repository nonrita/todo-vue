<script setup >
import { ref } from 'vue'

let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML', done: true },
  { id: id++, text: 'Learn JavaScript', done: true },
  { id: id++, text: 'Learn Vue', done: false }
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
  <main>
    <form class="todo-input-area" @submit.prevent="addTodo">
      <input
        class="todo-input"
        type="text"
        size="32"
        maxlength="32"
        required
        placeholder="Please enter new Todo"
        v-model="newTodo"
      />
      <button class="add-button"><FontAwesome icon="add" /></button>
    </form>

    <ul class="todo-list">
      <li class="todo-item" v-for="todo in todos" :key="todo.id">
        <div class="todo-item-left">
          <input type="checkbox" v-model="todo.done">
          <h1 :class="{ done: todo.done }">{{ todo.text }}</h1>
        </div>
        <div class="todo-item-right">
          <button @click="removeTodo(todo)"><FontAwesome class="trash-icon" icon="trash" /></button>
        </div>
      </li>
    </ul>
  </main>
</template>

<style>
main {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  padding: 24px 25% 0 25%;
  gap: 24px;
  .todo-input-area {
    display: flex;
    justify-content: center;
    gap: 16px;
    .todo-input {
      height: fit-content;
      padding: 0.5em 1em;
      border: 1px solid #afafaf;
      border-radius: 2.5em;
    }
    .add-button {
      background-color: #000;
      color: #fff;
      border-radius: 20px;
      height: 40px;
      aspect-ratio: 1 / 1;
    }
  }
  .todo-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    margin: 0;
    padding: 0;
    gap: 24px;
    .todo-item {
      display: flex;
      justify-content: space-between;
      align-items: end;
      padding: 0 16px 8px 8px;
      border-bottom: 1px solid #000 ;
      .todo-item-left {
        display: flex;
        gap: 8px;
        height: fit-content;
        h1 {
          font-size: 1.5rem;
        }
        .done {
          text-decoration: line-through;
        }
      }
      .todo-item-right {
        button {
          background-color: transparent;
          border: transparent;
          height: fit-content;
          padding: 0;
          .icon {
            height: 24px;
          }
        }
      }
    }
  }
}
</style>
