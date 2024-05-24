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

    <ul class="todo-list">
      <li class="todo-item">
        <div class="todo-item-left">
          <input type="checkbox" name="i" id="">
          <h1>Reactの勉強</h1>
        </div>
        <div class="todo-item-right">
          <button><fa class="icon" icon="trash" /></button>
        </div>
      </li>

      <li class="todo-item">
        <div class="todo-item-left">
          <input type="checkbox" name="i" id="">
          <h1>Reactの勉強</h1>
        </div>
        <div class="todo-item-right">
          <button><fa class="icon" icon="trash" /></button>
        </div>
      </li>

      <li class="todo-item">
        <div class="todo-item-left">
          <input type="checkbox" name="i" id="">
          <h1>Reactの勉強</h1>
        </div>
        <div class="todo-item-right">
          <button><fa class="icon" icon="trash" /></button>
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
