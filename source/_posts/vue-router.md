---
title: vue-router
date: 2018-05-25 19:28:46
tags: vue
---

#  vue-router

1. 相当于a标签，to里的路径就是a的href

```jsx
<router-link tag='li' to='/foo'>
	<a>/foo</a>
</router-link>
```

2. 更改路由

```jsx
<router-link to="/home3">home</router-link>
<router-link :to="{ path: 'home2' }">home</router-link>
```



```jsx
<!-- 命名的路由 -->
<router-link :to="{ name: 'user', params: { userId: 123 }}">User</router-link>

<!-- 对应的routes -->
const router = new VueRouter({
  routes: [
    {
      path: '/user/:userId',
      name: 'user',
      component: User
    }
  ]
})
```



```jsx
<!-- 带查询参数，下面的结果为 /register?plan=private -->
<router-link :to="{ path: 'register', query: { plan: 'private' }}">Register</router-link>
```

