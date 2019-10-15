# Action
Action 是把数据从应用（译者注：这里之所以不叫 view 
是因为这些数据有可能是服务器响应，用户输入或其它非 view 的数据 ）
传到 store 的有效载荷。它是 store 数据的唯一来源。
- 在 Redux 中的 action 创建函数只是简单的返回一个 action:
```JS
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
- 不同的是，Redux 中只需把 action 创建函数的结果传给 dispatch() 方法即可发起一次 dispatch 过程。
# reducer
- reducer是一个纯函数，接收旧的state和action，返回新的state

