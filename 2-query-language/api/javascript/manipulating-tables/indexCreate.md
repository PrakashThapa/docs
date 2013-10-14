---
layout: api-command 
permalink: api/javascript/index_create/
command: indexCreate
---

{% apibody %}
table.indexCreate(indexName[, indexFunction]) → object
{% endapibody %}

Create a new secondary index on this table.

__Example:__ To efficiently query our heros by code name we have to create a secondary
index.

```js
r.table('dc').indexCreate('code_name').run(conn, callback)
```


__Example:__ A compound index can be created by returning an array of values to use as
the secondary index key.

```js
r.table('dc').indexCreate('parental_planets', function(hero) {
    return [hero('mothers_home_planet'), hero('fathers_home_planet')];
}).run(conn, callback)
```


__Example:__ A multi index can be created by passing an optional multi argument. Multi
indexes functions should return arrays and allow you to query based on whether a value
is present in the returned array. The example would allow us to get heroes who possess
a specific ability (the field 'abilities' is an array).


```js
r.table('dc').indexCreate('abilities', {multi:true}).run(conn, callback)
```
