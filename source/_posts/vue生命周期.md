---
title: vue的生命周期
date: 2018-05-28 19:28:46
tags: vue
---

# VUE生命周期

##### vue生命周期总共分为8个部分  创建前/后,  载入/前后,  更新前/后,  销毁/后  



###### 1.创建前/后 : 

在beforeCreate阶段，vue实例的挂载元素el还没有。这个阶段可以添加loading事件，

在created阶段发起后端请求，拿回数据。

###### 2.载入前/后

在beforeMount阶段，vue实例的$el和data都初始化，但是挂载之前为虚拟的dom节点，data.message还未替换，页面无重新渲染。

在mounted阶段，vue实例挂载完成，data.message成功渲染。

###### 3.更新前/后

当data变化时，会触发beforUpdate和updatad方法。

###### 4.销毁前/后

在执行destroy方法后，对data的改变不会再触发周期函数，说明此时vue实例已经解除了事件监听以及和dom的绑定，但是dom解构依然存在。

