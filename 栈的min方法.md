```javascript
function MinStack(){

let data_stack =new Stack.Stack();
let min_stack =new Stack.Stack();
    //push方法
    this.push=function(item){
    if(min_stack.isEmpty()||item<min_stack.top()){
        min_stack.push(item);
    }else{
     	min_stack.push(min_stack.top());   
    }
	};
    //弹出栈顶元素
    this.pop =function(){
        data_stack.pop();
        min_stack.pop();
    };
    //返回栈的最小值
	this.min =function(){
    return min_stack.top();
	};
};
```

