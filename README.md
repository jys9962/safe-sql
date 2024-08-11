

```typescript
const { sql, params } = SQL`SELECT * FROM members where id = ${1}`;

console.log(sql); // SELECT * FROM members where id = ?
console.log(params); // [1]
```

```typescript
const subQuery = SQL`SELECT * FROM members where id = ${1} `;
const { sql, params } = SQL` SELECT * FROM (${subQuery}) where name = ${'name'} `;

console.log(sql); // SELECT * FROM (SELECT * FROM members where id = ?) where name = ?
console.log(params); // [1, 'name']
```
