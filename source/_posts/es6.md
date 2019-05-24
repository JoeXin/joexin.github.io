---
title: ES6基本语法
date: 2019-5-24
tags: [es6]
---

#### ES6基本语法[抄录]

1.  let

let作用域只限于当前代码块

```
{
    let a = 12;
}
console.log(a);  //报错啦
```

let声明的变量作用域不会被提升

```
{
    console.log(a);  //报错
    let a = 12;
}
```

在相同的作用域下不能声明相同的变量

```
 {
   let a = 10;
   let a = 11;  //报错    
 }
```

for循环体现let的父子作用域

```
  //使用var声明，需要用到“闭包”
    var btns = document.querySelectorAll("button");
      for(var i=0;i<btns.length;i++){
      （function(i){
           btns[i].onclick= function (){
            alert("点击了"+i+"个按钮")
          }
      })(i);
    }
    
    //let声明
     let btns = document.querySelectorAll("button");
      for(let i=0;i<btns.length;i++){
          btns[i].onclick= function (){
            alert("点击了"+i+"个按钮")
          }
      }
```
2. const

1 >  const作用域只限于当前代码块

2 >  const声明的变量作用域不会被提升

3 > 在相同的作用域下不能重复声明

4 > 声明的同时必须赋值，声明后值无法改变

```
{   
    const b; //报错
    
    const a = 123;
    a = 222; //报错
    
} 
```


```
{
    const obj = {
        name:"lisi"
     }
    console.log(obj.name); //lisi
    
    obj.name = "joexin";
    console.log(obj.name);//joexin
}
//在上面中定义的是一个常量对象，对象是储存在内存的“堆区”，通过一个地址描述出来，在“栈区”关联此地址。所以，obj存储的是地址，而不是值，是可以做修改的。
```