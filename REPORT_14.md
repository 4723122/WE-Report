# Webエンジニアリング演習 第14回 レポート

## 学籍番号
4723122

## 実装したコード

index.ts
```
import TodoListView from '../views/TodoListView.vue'
import About from '../views/About.vue'
import TodoDetail from '../views/TodoDetail.vue'

const routes = [
    { path: '/', name: 'TodoList', component: TodoListView },
    { path: '/todos', name: 'TodoListAlias', component: TodoListView },
    { path: '/about', name: 'About', component: About },
    { path: '/todos/:id', name: 'TodoDetail', component: TodoDetail }
]
```

TodoListView.vue
```
      <ul>
        <li
          v-for="todo in todoStore.todos"
          :key="todo.id"
          style="display: flex; align-items: center; gap:0.5rem; margin: 0.25rem 0;"
        >
          <input type="checkbox" v-model="todo.completed" />
          <span :style="{ textDecoration: todo.completed ? 'line-through' : 'none' }">
            <RouterLink :to="{name: 'TodoDetail', params: { id: todo.id }}">{{ todo.title }}</RouterLink>  
          </span>
          <button @click="todoStore.removeTodo(todo.id)">Remove</button>
        </li>
      </ul>
```

TodoDetail.vue
```
<script setup lang="ts">
import { useRoute } from 'vue-router';
import { useTodoStore } from '../stores/todoStore'; //storeのインポート
import AddTodo from '../components/AddTodo.vue';
const todoStore = useTodoStore(); //storeの使用
const route = useRoute();
const id = route.params.id;
</script>

<template>
    <section>
        <h2>Todos</h2>
        {{ todoStore.todos[id-1] }}
    </section>

</template>
```

