---
title: npm script -- 如何在package.json设置环境变量
tags:
  - npm script
  - nodejs
categories:
  - npm
---

{% cq %} 爱情是女人一生的历史，而只是男人一生中的一段插曲 
 ---史达尔 
{% endcq %}

## 在npm scripts里设置环境变量

```
"scripts": {
    "prod": "NODE_ENV=production electron .",
    "dev": "NODE_ENV=development electron ."
  }
```

## 使用如下方式获取环境变量

```
npm run dev
console.log(process.env.NODE_ENV) //development

npm run prod
console.log(process.env.NODE_ENV) //production
```
