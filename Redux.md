![1568106373499](H:\book\images\1568106373499.png)



安装Redux

```
//安装rudex
npm install --save redux

在src目录下创建文件夹 store
store文件夹下创建 store.jsx 和 reducer.jsx

简单使用redux

在store.jsx中输入
import reducer from './reducer'
import { createStore } from 'redux'			//createStore是redux中的一个方法
const store = createStore(				   
    reducer,							  
    window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__()
    );
export default store

在ruducer.jsx中输入
const defaultState = {}							//state的默认值
export default (state=defaultState, action) =>{
	//可以写入逻辑判断
	return state;
}
```



```
获取state
使用JSON的深度复制一个对象并赋值到 newState 中

let newState = JSON.parse(JSON.stringify(state));
```

```
如果使用input并且使用value属性时，需要进行设置
    constructer(){
		this.storeChange = this.storeChange.bind(this);
    	store.subscribe(this.storeChange);
	}
	
	storeChange(){
		this.setState( store.getState);
	}
    
```

```
对事件进行监听

changeInputValue(e){
    // console.log(e.target.value)
    const action = {
      type: "InputValue",					//设置类型，使reducer的匿名函数可以通过type进行逻辑判断
      value: e.target.value
    }
    store.dispatch(action);					//将action传入到 store 中，使reducer可以使用匿名函数时可以获取到参数 action 的值。
  }

```

```
删除使用splice()函数
参数1: 需要删除的索引;
参数2: 需要删除的个数。

eg:
	newState.list.splice(action.index, 1);
```

```
store.subscribe(this.storeChange);
```

