---
layout: api-command 
permalink: api/javascript/expr/
command: expr
---

{% apibody %}
r.expr(value) → value
{% endapibody %}

Construct a RQL JSON object from a native object.

__Example:__ Objects wrapped with expr can then be manipulated by RQL API functions.

```js
r.expr({a:'b'}).merge({b:[1,2,3]}).run(conn, callback)
```


__Example:__ In JavaScript, you can also do this with just r.

```js
r({a: 'b'}).merge({b: [1,2,3]}).run(conn, callback)
```
