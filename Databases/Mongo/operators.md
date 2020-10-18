## $eq

Syntax: {field: {$eq: value} }

The $eq operator matches documents where the value of a field equals the specified value.

```
db.inventory.find( { qty: { $eq: 20 } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/eq/

<br/>

## $ne

Syntax: {field: {$ne: value} }

$ne selects the documents where the value of the field is not equal to the specified value. This includes documents that do not contain the field.

```
db.inventory.find( { qty: { $ne: 20 } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/ne/

<br/>

## $in

Syntax: { field: { $in: [<value1>, <value2>, ... <valueN> ] } }

The $in operator selects the documents where the value of a field equals any value in the specified array.

```
db.inventory.find( { qty: { $in: [ 5, 15 ] } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/in/

<br/>

