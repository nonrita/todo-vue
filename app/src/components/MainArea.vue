<script></script>

<template>
  <main>
    <form class="todo-input-area">
      <input
        class="todo-input"
        type="text"
        size="32"
        maxlength="32"
        required
        placeholder="Please enter new Todo"
      />
      <button class="add-button"><fa icon="add" /></button>
    </form>
  </main>
</template>

<style>
main {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 24px 20% 0 20%;
  .todo-input-area {
    width: fit-content;
    display: flex;
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
}
</style>
