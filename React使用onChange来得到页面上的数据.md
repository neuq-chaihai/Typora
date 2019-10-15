# **必须先绑定onChange事件**

原因：React使用单项数据流，所以文本框现在时readOnly只读状态，在绑定onChange，通过处理函数可以获得文本框中的内容





1. 使用document.getElementById来获取页面上的内容

2. 使用ref来获取

   ​	eg: <input type="text" value={this.state.contence} onChange={处理的函数} ref="txt" />

   ​	使用**this.refs.txt.value**获取

3. 给处理函数加上参数e,使用

   ​		**e.target.value**来获取文本框中的内容