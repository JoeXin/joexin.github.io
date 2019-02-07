---
title: Js页面跳转的几种方式
date: 2017-5-29
tags: [JavaScript]
---


### Js页面跳转的几种方式

#### 第一种

```
<script language="javascript">
 	window.location.href='https://www.baidu.com'
</script> 
```

#### 第二种

```
<script language="javascript">
 	window.history.back(-1);
</script>  
```

#### 第三种

```
<script language="javascript">
 	window.navigate("top.jsp");
</script>  
```
 **这种只支持IE浏览器**

#### 第四种

```
<script language="javascript">
 	self.location='top.htm';
</script>     
```

#### 第五种

```
<script language="javascript">
 	top.location='xx.jsp';
</script>  
```