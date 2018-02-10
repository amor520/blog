---
title: mongodb批量更新
tags:
  - mongodb批量更新
categories:
  - mongodb
---

{% cq %} 生活中没有旁观者的 {% endcq %}

momgodb批量更新操作

## version<2.2

```
db.users.update(
{userid: {$in: ['1','2','3']}},
{$inc: {mycounter: 1}},
false, true
);
```
## version>2.2

```
db.users.update(
{userid: {$in: ['1','2','3']}},
{$inc: {mycounter: 1}}, 
{{multi: true}}
);
```
{% fi https://olb7pgc09.qnssl.com/wallhaven-69371.jpg, mongodb, mongodb %}