# 第13回 Webエンジニアリング演習 レポート
## 学籍番号 
 4723122
## 実装したコード
todoStore.tsに追加したコード
```
    const removeTodo = (id: number) => {
        todos.value = todos.value.filter(todo => todo.id !== id)
    }

    return { todos, addTodo, removeTodo }

```


App.vueに追加したコード
```
          <button @click="todoStore.removeTodo(todo.id)">Remove</button>
```
