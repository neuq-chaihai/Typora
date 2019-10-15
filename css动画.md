```
html代码:

class App extends React.Component {
  constructor(props){
    super(props);
    this.state = {
      see: true
    }
    this.ChangeSee = this.ChangeSee.bind(this);
  }

  ChangeSee(){
    this.setState({
      see: this.state.see?false:true
    })
  }

  render(){
    return (
      <Fragment>
        <h1 className={this.state.see? "show": "hidden"}>Hello</h1>
        <input type="button" value="切换形态" onClick={this.ChangeSee}/>
      </Fragment>
    );
  }
}
```

```
css代码:

.hidden{
  animation: hidden-item 2s ease-in forwards;
}

.show{
  opacity: 1;
  transition: all 1s ease-in;
}

@keyframes hidden-item{
  0%{
    opacity: 1;
    color: red;
  }
  50%{
    opacity: 0.5;
    color: green;
  }
  100%{
    opacity: 0;
    color: pink;
  }
}
```

