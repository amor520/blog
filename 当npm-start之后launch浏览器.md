---
title: npm script -- 当npm start之后launch浏览器
tags:
  - npm script
categories:
  - npm
---

{% cq %}
精神像乳汁一样可以养育人的，智慧便是一只乳房。
 ---  雨果
{% endcq %}
```
// Windows
"start":"start http://localhost:8081 & node bin/www"

// Mac
"start":"open http://localhost:8081 && node bin/www"

// Linux
"start":"xdg-open http://localhost:8081 && node bin/www"
```